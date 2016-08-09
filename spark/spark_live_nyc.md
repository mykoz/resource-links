##Spark Live - NYC 
8/9/16  
https://databricks.com/spark-live/new-york-ny  

###Databricks as a Company
* founded by creators of Apache Spark (at Berkeley)
* 

* Just-in-Time Data Platform (AGILE)
  * data and compute are separated
  * integrate existing data stores
  * efficient cache on first access

* Integrated Workspace (Democratize Big Data)
  * interactive notebooks, dashboards, reports
  * real-time exploration, machine learning, graph use cases

* Automated Apache Spark Management (Production-ready)
  * workflow scheduler for ML

###Upcoming Databricks Features
* beta feature:  allows you to auto-scale cluster
* cluster will auto-scale down to save on costs
* fully compatible with AWS pricing
* Databricks has been written by open-source Spark team

* Workspace:
* graphs library - takes in dataframes rather than traditional RDDs
* open up notebook, attach to Spark cluster that was previously created
* can see the number of partitions in the dataframe, can see how the job is doing, by partition
* can create Library, then can Search Packages (Spark-Packages)
* click, create library, then attach to cluster
* Databricks is meant to be a collaborative environment for your organization. can add users with different levels of access.
  * Workspace Access Control
  * Cluster Access Control
* can share, collaborate

* 
https://databricks.com/blog/2016/03/16/on-time-flight-performance-with-graphframes-for-apache-spark.html  
dashboard:  name our dashboard  
can schedule notebook in production  
Vida Ha, Solutions Architect  
* can set email alert options, time out, retry it
* langs:  python, scala, r, java
* ? can't download notebooks, will spin out a micro-cluster of 6 GB, 6 nodes on Community Edition
* 50-60 GB of data might be doable on 6GB cluster, depends on data
* small cluster pricing is reasonably free
* On-demand instance, Spot instance (market rate)
* For professional edition, < 1 hour set up , can connect to AWS, then it works right out of the box, meant to be a managed service


* under a minute, you can create a Spark cluster
* comes up in AWS account
* 

###Future of Databricks
Bringing Apache Spark to the Enterprise  
Maddie Schults, Product Manager  

* Percent of Big data projects that will fail thru 2017 is 60%  
* Goal of Databricks:  How do we minimize your cost and time so you can get to actionable insights with your data?
* Spark is cloud-agnostic, can move workload to any cloud platform

####Major Features in Spark 2.0
* released July 2016
* Performance - Tungsten Phase 2 speedups of 5-20x
* Structured Streaming Engine
* SQL 2003 & Machine Learning - full SQL support, a lot more machine learning support
* 

Databricks - managed Spark cluster that provides a collaborative environment  
####Near-Term Roadmap
* single-sign on
* Advanced Analytics
  * support vis libraries:  plot.ly, bokeh
  * 3rd party ML integrations:  sci-kit learn, tensor flow (deep learning)
  

###Amazing Analytics from Silicon to Software — Intel
Meena Arunachalam  
Intel, Principal Engineer  
(from West Coast)  

###
Basho  
Alexander Sicular

---

#Technical Training
http://tinyurl.com/NYCSparkLive   
Instructor:  Jacob Parr

in cell:  
```
%python
1 + 1
```
keyboard - list of shortcuts  
Publish - can share code  
Comments - can add comments  
Revision History  

Home button - to my account folder  
Application Examples - tons of examples  
Database Guides  
Library - where we have libraries  
Spark-Live - name of our course  

datasets_mount  
creates links from AWS to here, to bring in datasets  
ReadMe - version of notebook we've gone through, executed code, to follow along, everything is run   
RunMe - version we will work with for majority of class, code is already there, 90% of it, 
DE - data engineer  
DA - data analysis  
DS - 

Driver / Executor  

JVM = Java Virtual Machine  
