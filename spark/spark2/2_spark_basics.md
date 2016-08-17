#Spark Basics
  
###Interactive Spark has been launched with `bin/pyspark`

```bash
reshama$ bin/pyspark
Python 2.7.6 (default, Sep  9 2014, 15:04:36) 
[GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.39)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel).
16/08/15 13:11:34 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /__ / .__/\_,_/_/ /_/\_\   version 2.0.0
      /_/

Using Python version 2.7.6 (default, Sep  9 2014 15:04:36)
SparkSession available as 'spark'.
>>> 
```
###Confirm spark context is there by typing `sc`:  
```bash
>>> sc
<pyspark.context.SparkContext object at 0x107083e50>
```



###To exit interactive Spark, type `exit()`:   
```bash
>>> exit()
reshama$ 
```




 
