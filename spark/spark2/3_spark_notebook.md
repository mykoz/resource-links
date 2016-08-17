##Spark Notebook Configuration

https://districtdatalabs.silvrback.com/getting-started-with-spark-in-python  



####In your bash_profile file:  
```bash
reshama$ emacs ~/.ipython/profile_spark/startup/00-pyspark-setup.py
```

```bash
# spark set up                                                                  
export SPARK_HOME=/Users/rshaikh/apps/spark/spark-2.0.0-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH
export PYTHONPATH=$SPARK_HOME/python/lib/py4j-0.10.1-src.zip:$PYTHONPATH
export PYSPARK_SUBMIT_ARGS="--master local[2]"
```
```
reshama$ source ~/.bash_profile
```

Read up on this:  
Minimizing the Verbosity of Spark  

Create an iPython notebook profile for our Spark configuration.  
```bash
$ ipython profile create spark
```
  
```bash
echo $SPARK_HOME 
echo $PATH
echo $PYTHONPATH
```


```bash
reshama$ echo $SPARK_HOME 
/Users/rshaikh/apps/spark/spark-2.0.0-bin-hadoop2.7
reshama$ 
```


####Errors
**`--profile` error
If you get this error:  
```bash
[C 13:36:56.092 NotebookApp] Bad config encountered during initialization:
[C 13:36:56.093 NotebookApp] Unrecognized flag: '--profile'
```
[Profiles Not Supported Anymore in IPython Notebooks](http://stackoverflow.com/questions/34530276/profiles-not-supported-anymore-in-ipython-notebooks)  

try going back to older version of notebook:  
```bash
pip install ipython[notebook]==3.2.3
```
