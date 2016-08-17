#Spark on AWS:  Launching a cluster on EC2


The following is based off of:
http://spark.apache.org/docs/latest/ec2-scripts.html

Navigate to the ec2 directory within your Spark directory

```sh
./spark-ec2 -k <keypair> -i <key-file> -s <num-slaves> launch <cluster-name>
```


Most importantly, remember to kill the cluster when you are done with it otherwise you may start to build up a bill

```sh
./spark-ec2 -i <keypair_file> destroy <cluster_name>
```

More complete instructions are available at [AMPLab Tutorials](http://ampcamp.berkeley.edu/4/exercises/launching-a-bdas-cluster-on-ec2.html)


