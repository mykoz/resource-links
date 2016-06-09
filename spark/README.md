###References

[Max Melnick blog on setting up notebook in docker on AWS](http://maxmelnick.com/2016/06/04/spark-docker.html)

###Spark Plaforms
* locally (download the source from github or Apache)
* Cloudera (need Virtual Box or VM Ware Fusion Pro)
* Microsoft Azure
* Hortonworks Virtual Machine
* [Interactive and Reactive Data Science using **Scala and Spark (no python)** (Created by andypetrella)](http://spark-notebook.io/)

###Spark

Hadoop
* MapReduce
* HDFS
* Many companies are so entrenched in Hadoop, it is hard to change directions

Spark
* has no HDFS, built to work with Hadoop (some say core of HDFS is hadoop)
* is better than mapreduce part of hadoop

Spark is faster than Hadoop
* Spark doesn't have to write to disk when running a job
* Spark uses in-memory caching

RDD 
* think of these as our main data types

using `spark context` to turn data array into RDD, means it is serialized.  we are able to partition it out.

PySpark SQL


