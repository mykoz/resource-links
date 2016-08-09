
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
If you comment out `show()`, nothing will happen.  It won't execute.  


####Transformations:
* select
* distinct
* groupBy
* sum
* orderBy
* filter
* limit

####Actions:  
* show
* count
* collect
* save

can tab after the dot to see all the different operations  
`pagecountsEnAllDF.filter($"project$" === "en")`  

`$` is Scala way of saying this is a column object.  
= assignment  
==  
===    (lazy = operation, evaluate it later)  

transformation - lazy  
action - executes

####`display` is a Databricks feature; lot of functionality from that display option  
```
// Display the DataFrame as a HTML table so it's easier to read
display(pagecountsEnWikipediaDF.orderBy($"requests".desc).limit(25))
```  

####Data Import

JDBC (Cassandra, etc)  
Table / Create Table / Data Import  

We can import file directly with this command: 
```
val tempDf = sqlContext.read
   .format("com.databricks.spark.csv")
   .option("header", "true")        // Use first line of all files as header
   .option("inferSchema", "true")   // Automatically infer data types
   .option("delimiter", "\t")       // Use tab delimiter (default is comma-separator)
   .load("/mnt/wikipedia-readonly/pageviews/pageviews_by_second.tsv")

tempDf.registerTempTable("pageviews_by_second")
```

Spark dataframe does allow nested columns in data (versus flat file)  


`printSchema()` prints out the schema for the table, the data types for each column and whether a column can be null:  
`pageviewsDF.printSchema`  

####Partitions and Tasks
DataFrames are made of one or more partitions. To see the number of partitions a DataFrame is made of:
```
pageviewsDF.rdd.partitions.size
```


Count the number of records (rows) in the DataFrame:
`pageviewsDF.count`  







