
###RDDs (telling your software how to do it)

01-DA-Pagecounts  
Create a DataFrame  

```
%fs ls /mnt/wikipedia-readonly/pagecounts/staging_parquet_en_only/
```
fs = file system  
ls = list  

```
val pagecountsEnAllDF = sqlContext.read.parquet("/mnt/wikipedia-readonly/pagecounts/staging_parquet_en_only/")
```
sc = spark context  
sqlContext.read.parquet - reader that reads parquet file
parquet file - csv file without data types  

`val pagecountsEnAllDF` - creating a Scala variable  

`pagecountsEnAllDF.show(10)` - executes a command, `show` is a command  


####printSchema() prints out the schema for the DataFrame, the data types for each column and whether a column can be null:  
`pagecountsEnAllDF.printSchema`  

####Count the number of total records (rows) in the DataFrame:  
`pagecountsEnAllDF.count`  

####transformations - are considered lazy  
####action -  when those transformations are actually executed  
```
pagecountsEnAllDF
  .select($"project", $"requests")   //transformation
  .groupBy($"project")               //transformation
  .sum()                             //transformation
  .orderBy($"sum(requests)".desc)    //transformation
  .show()                            //action
```

Transformations:
* select
* distinct
* groupBy
* sum
* orderBy
* filter
* limit

Actions:  
* show
* count
* collect
* save





