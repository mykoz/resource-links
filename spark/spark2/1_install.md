
Last updated:  8/15/16  

Spark Installation:

Source:  
http://ramhiser.com/2015/02/01/configuring-ipython-notebook-support-for-pyspark/

##Installing Spark

###Requirements
####Java
Check if Java is installed
```bash
reshama$ java --version
No Java runtime present, requesting install.
```
For me, it is not, so I will install from Java website:  
Java source file:  https://java.com/en/download/  
Java installation instructions:  https://java.com/en/download/help/mac_install.xml  


http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

####Spark
1.  http://spark.apache.org/downloads.html  
    * Choose a Spark release:  2.0.0
    * Download Spark: spark-2.0.0-bin-hadoop2.7.tgz (click on spark-... link and download)
    * Expand the spark-2.0.0-bin-hadoop2.7.tgz file with `tar zxvf spark-2.0.0-bin-hadoop2.7.tgz`

```bash
reshama$ pwd
/Users/rshaikh/apps
reshama$ ls -Glp
total 0
drwxr-xr-x  3 rshaikh  staff  102 Apr 27 12:16 mongodb/
drwxr-xr-x  3 rshaikh  staff  102 Aug 15 12:31 spark/
reshama$ 
```
I am now in this folder:  
```bash
reshama$ pwd
/Users/rshaikh/apps/spark
reshama$ ls
spark-2.0.0-bin-hadoop2.7.tgz
reshama$ 
```
Next, expand the `*.tgz` file:  
```bash
reshama$ tar zxvf spark-2.0.0-bin-hadoop2.7.tgz
```
Run `bin/pyspark`  
```bash
reshama$ pwd
/Users/rshaikh/apps/spark/spark-2.0.0-bin-hadoop2.7
reshama$ bin/pyspark
```









---

not sure of this:  
https://www.supergloo.com/fieldnotes/apache-spark-ipython-notebook-easy-way/  
