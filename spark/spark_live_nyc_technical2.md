

https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175194/4592099822616319/latest.html

####Reading from Disk vs Memory

The 255 MB pageviews file is currently on S3, which means each time you scan through it, your Spark cluster has to read the 255 MB of data remotely over the network.  

---

https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175563/4592099822616319/latest.html  


%sh is a magic command in Databricks to run shell commands in the container.
Check how much memory is free on the EC2 machine:  
%sh free -mh  

The jps tool lists the Java Virtual Machines (JVMs) in the container:  
%sh jps  

DriverDaemon above is the actual 3.7 GB Spark JVM. Ignore jps in the output above as it's just the jps command running. We'll cover ChauffeurDaemon soon.
jps -v prints verbose details about each JVM:  
%sh jp

