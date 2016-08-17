#Spark Basics
  
##Interactive Spark has been launched with `bin/pyspark`

**Note:**  make sure you are in the appropriate directory.  
```bash
reshama$ pwd
/Users/rshaikh/apps/spark/spark-2.0.0-bin-hadoop2.7
reshama$ bin/pyspark
```  

##Confirm spark context is there by typing `sc`:  
```bash
>>> sc
<pyspark.context.SparkContext object at 0x107083e50>
```

##Spark Basics

We connect to Spark functionality via the “Spark Context” available at `sc`. One way to populate an RDD is via `.textFile`. Let's see lazy evaluation in action.

```python
data = sc.textFile('/nope/no/file/here')
```

This appears to succeed. We won't find out that it's broken until we access the RDD.

```python
data.first()
# ERROR
```

Let's get some real data:

```python
data = sc.textFile('/Users/.../nyc16_ds6/09-kojak1/04-kojak/input.txt')
```

Spark conveniently lets us access our usual file system. You can also get at things in HDFS just by using `hdfs://`

Some operations bring RDD contents into local Python memory. The `.collect` method does this for the whole RDD.

```python
data.take(2)
# a list containing the first two lines
```


Spark's interface is functional, so things like `map` are present in droves.

```python
handle_tuples = data.map(lambda x: (eval(x)['user']['screen_name'], 1))
results = handle_tuples.reduceByKey(lambda a, b: a+b)
results.collect()
## [(u'NuriaMariaT', 3),
##  (u'IBMBigDataUK', 2),
##  (u'EXINMUSICA', 3),
##  (u'daniel_junior_s', 1),
##  (u'hoisamu0619', 1),
##  (u'JennZimm72', 4),
##  (u'anhldbk', 2),
##  (u'___louder', 2),
##  (u'RobinToubac', 3),
##  (u'ValueRecovery', 2),
##  (u'RedPaTo2', 2)]
```

We can set 4 partitions  
```python  
data = [1, 2, 3, 4, 5]
distData = sc.parallelize(data,4)
distData.reduce(lambda a, b: a + b)
```


### Data Frames

To run Spark with extra CSV magic, use the [spark-csv](https://github.com/databricks/spark-csv) library. Currently, this means starting PySpark as:


```bash
bin/pyspark --packages com.databricks:spark-csv_2.10:1.2.0
```

Spark's SQL-like functionality is accessed via its `SQLContext`. You have one provided inside `pyspark`.

Now we can do such magical things as this:

```python
df = sqlContext.load(source="com.databricks.spark.csv", header="true", path ='/Users/.../nyc16_ds6/09-kojak1/04-kojak/AllstarFull.csv')
df
## DataFrame[playerID: string, yearID: string, gameNum: string, gameID: string, teamID: string, lgID: string, GP: string, startingPos: string]
```


Amazing!

```python
from pyspark.sql.types import IntegerType
df2 = df.withColumn('year', df.yearID.cast(IntegerType()))
df2.describe().show()
## summary year
## count   4912
## mean    1975.216815960912
## stddev  23.053109669462515
## min     1933
## max     2013
```

So convenient!

```python
df2.groupBy('playerID').agg({'year': 'mean'}).take(10)

##  [Row(playerID=u'siebedi01', AVG(year)=1943.0),
##  Row(playerID=u'runnepe01', AVG(year)=1960.0)
##  Row(playerID=u'herrmed01', AVG(year)=1974.0),
##  Row(playerID=u'davalvi01', AVG(year)=1965.0),
##  Row(playerID=u'goodmbi01', AVG(year)=1951.0),
##  Row(playerID=u'perezod01', AVG(year)=2002.0),
##  Row(playerID=u'ugglada01', AVG(year)=2008.666666666667),
##  Row(playerID=u'tettlmi01', AVG(year)=1991.5),
##  Row(playerID=u'jacksgr01', AVG(year)=1969.0),
##  Row(playerID=u'bluevi01', AVG(year)=1977.0)]
```


So data frame! There's even a `.join` ([docs](https://spark.apache.org/docs/latest/api/python/pyspark.sql.html#pyspark.sql.DataFrame.join)).




###To exit interactive Spark, type `exit()`:   
```bash
>>> exit()
reshama$ 
```




 
