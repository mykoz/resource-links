###Apache Spark Workshop

What is distributed computing?  
 * connecting across multiple computers to increase efficiency.
 * it is the heart of solving big data problems

What is Spark and why is it important?  
 * Spark APIs to code in Python (PySpark), R, Java, Scala
 * SparkSQL for relational data querying
 * MLlib for machine learning
 * GraphX for graph processing (page rank)
 
 ####MapReduce
 * Map:  Assigns each word to its frequency
 * Reduce:  
 
 Spark can be 100x faster than MapReduce due to in-memory processing
 
 ```bash
 ```
 
 Spark Context (SC):  must be created at the start of Spark session  
 Resilient Distributed Dataset (RDD):  data across cluster nodes that can be acted on in parallel
  * 
 

```bash
reshama$ pwd
/Users/reshamashaikh/Apps
reshama$ ls
total 35728
drwxr-xr-x@ 20        680 Feb 28 19:50 hadoop-2.7.2-src
-rw-r--r--@  1   18290860 Feb 28 19:50 hadoop-2.7.2-src.tar.gz
drwxr-xr-x@ 27        918 Feb 25 17:53 spark-1.5.2-bin-hadoop2.6
drwxr-xr-x  17        578 Feb 27 00:02 spark-1.6.1-bin-hadoop2.6
drwxr-xr-x@ 12        408 Mar 20 21:11 spark-notebook-0.6.2-scala-2.10.4-spark-1.6.0-hadoop-2.2.0
reshama$ export SPARK_HOME=~/Apps/spark-1.6.1-bin-hadoop2.6/
reshama$ echo $SPARK_HOME
/Users/reshamashaikh/Apps/spark-1.6.1-bin-hadoop2.6/
reshama$ 
```
