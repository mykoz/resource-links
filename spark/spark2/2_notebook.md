##Spark Notebook Configuration

https://districtdatalabs.silvrback.com/getting-started-with-spark-in-python  

####In your bash_profile file:  
```bash
# spark set up                                                                  
export SPARK_HOME=/Users/rshaikh/apps/spark/spark-2.0.0-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH
export PYTHONPATH=$SPARK_HOME/python/lib/py4j-0.10.1-src.zip:$PYTHONPATH
export PYSPARK_SUBMIT_ARGS="--master local[2]"
```

