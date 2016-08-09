

https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175194/4592099822616319/latest.html

####Reading from Disk vs Memory

The 255 MB pageviews file is currently on S3, which means each time you scan through it, your Spark cluster has to read the 255 MB of data remotely over the network.  

---

https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175563/4592099822616319/latest.html  


%sh is a magic command in Databricks to run shell commands in the container.
Check how much memory is free on the EC2 machine:  
`%sh free -mh`  

The jps tool lists the Java Virtual Machines (JVMs) in the container:  
`%sh jps`  

DriverDaemon above is the actual 3.7 GB Spark JVM. Ignore jps in the output above as it's just the jps command running. We'll cover ChauffeurDaemon soon.
jps -v prints verbose details about each JVM:  
`%sh jp`

sql = structured query language  

The explain() method can be called on a DataFrame to understand its physical plan:  
`in_out_ratioDF.explain()`

---

###Start with the Bonus Graph D3js Notebook, then return here...  
https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175084/4592099822616319/latest.html  

```

Before we can do anything, we need the Graph Frames API.
1. Open your workspace
Right-click > Create > Library
Change the source to Maven Coordinate
Click Search SparkPackages and Maven Central
Search for graphframes
Select the correct release
Click Select
Click Create Library
Click Attach automatically to all clusters.
10. Restart your cluster
```

###Explore English Wikipedia via DataFrames and RDD API
https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175725/4592099822616319/latest.html  



sparl.mllib  
* original lower level APIs
* 
vs  
spark.ml  
* newer "higher-level" API for constructing workflows
* built on top of DataFrames

New Circle - offers classes

TF-IDF  
lower the words that occur more frequently  

####K-means clustering
An unsupervised ML algorithm for classifying items into `k` groups.  
k:  the number of pre-chosen groups  

####Spark ML Pipeline
DataFrame:
Tokenizer()  
StopWordsRemover()  
hashingTF()  
IDF()  
normalizer() - articles may have higher scores if there are a lot more words
kmeans()  

####07-DS-Wiki-ML
https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175418/4592099822616319/latest.html  

####Set up the ML Pipeline


####Spark Streaming
about having a huge firehose of data thrown at you  
* runs micro-batches at fixed batch intervals
* batch processing time > batch interval
* 

When running on Databricks, the SparkContext is already created for us.  
`sc`  
Create a new `StreamingContext`, using the   

