#Hadoop (on AWS Ubuntu cloud server)

### Hadoop installation and setup on your cloud server

#### Set up a running AWS free tier instance

In AWS, start a free tier Ubuntu instance.  The default username for an ubuntu instance in AWS is ***ubuntu***.  We'll just use that for our purposes today, but you can go through the steps that we've done previously if you want to set up your own username(s).

ssh to your machine and follow the white rabbit below.

#### Install TextBlob

We're going to use it in our text processing, so make sure you have textblob in there.

First install pip:

```bash
sudo apt-get update
```

```bash
sudo apt-get install python-pip
```

Now install TextBlob

```bash
sudo pip install textblob
```


#### Install Java 7 (Hadoop-friendly for certain)

```bash
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-jdk7-installer
```

The java install will ask a few straightforward questions, just answer
them.


#### Check that java version is 1.7

```bash
java -version
```


####Create a Hadoop user

```bash
sudo addgroup hadoop
sudo adduser --ingroup hadoop hduser
```

This will ask for a password, give it one. Each user in unix has a
password. You will use that when you switch to that user.

Make an ssh key so hadoop can connect to machines with ssh without you
entering a password every time.  If managing a cluster, Hadoop needs to be able to reach all machines in the cluster via passwordless SSH, so you'd need to distribute these keys around to workers.

```bash
su hduser
ssh-keygen  -t rsa -P ""
```

(hit enter when asked where to save the key)

Add the key to recognized keys in all cluster nodes (only localhost
in this tutorial case, so no need to change machines).

```bash
cat $HOME/.ssh/id_rsa.pub >> $HOME/.ssh/authorized_keys
```

Add key to recognized keys list and test that it works without a
password

```bash
ssh localhost
```

(type yes and enter when it asks about adding the key print to the
known keys list)

Exit your ssh and hduser sessions:
``bash
exit
exit
```


#### Download and Install Hadoop

Your current user should be ubuntu (a root user, if you've set up a different one).  If it isn't, either `su ubuntu` or `exit` whatever current user you've switched to.

```bash
cd ~ 
wget http://mirrors.sonic.net/apache/hadoop/common/hadoop-2.7.1/hadoop-2.7.1.tar.gz
```

```bash
sudo tar xvzf hadoop-2.7.1.tar.gz
sudo mv hadoop-2.7.1 /usr/local/hadoop
cd /usr/local
sudo chown -R hduser:hadoop hadoop
```

#### Change bashrc settings

```bash
su hduser
emacs ~/.bashrc
```

You can use another editor, too, of course. (If you don't have emacs,
and do not want to use another editor you can install emacs with
*apt-get install emacs*). Add the following lines:

```text
# Environment variable for Hadoop location, include bin in the path
export HADOOP_HOME=/usr/local/hadoop
export PATH=$PATH:$HADOOP_HOME/bin

# Environment varibale for Java location
export JAVA_HOME=/usr/lib/jvm/java-7-oracle

# Hadoop related aliases
unalias fs &> /dev/null
alias fs="hadoop fs"
unalias hls &> /dev/null
alias hls="fs -ls"
```

Exit emacs (`Ctrl-x Ctrl-s` to save, `Ctrl-x Ctrl-c` to exit). Great, now these will run every time you connect to the
server, but let's also make sure they apply now. Type this in your
terminal.:

```bash
source ~/.bashrc
```


#### Create the place to put HDFS on and tell Hadoop where it is

```bash
su ubuntu
```

(We need some more sudo stuff so switch back to yourself for now, you could also `exit`)

```bash
sudo mkdir -p /app/hadoop/tmp
sudo chown -R hduser:hadoop /app/hadoop/tmp
su hduser
```

(back to hduser to edit the configuration files)

```bash
emacs /usr/local/hadoop/etc/hadoop/core-site.xml
```

Between `< configuration >`  and `< /configuration >` put this in:

```xml
<property>
<name>hadoop.tmp.dir</name>
<value>/app/hadoop/tmp</value>
      <description>A base for other temporary directories.</description>
</property>


<property>
<name>fs.default.name</name>
<value>hdfs://localhost:54310</value>
<description>The name of the default file system.  A URI whose
scheme and authority determine the FileSystem implementation.
The uri's scheme determines the config property (fs.SCHEME.impl)
naming the FileSystem implementation class. The uri's authority
is used to determine the host, port, etc. for a filesystem.</description>
</property>
```

Ok now another one.

```bash
emacs /usr/local/hadoop/etc/hadoop/mapred-site.xml.template
```

Between `< configuration >`  and `< /configuration >`  put this in:

```xml
<property>
<name>mapred.job.tracker</name>
<value>localhost:54311</value>
      <description>The host and port that the MapReduce job tracker
      runs
            at.  If "local", then jobs are run in-process as a single
            map
            and reduce task.
            </description>
            </property>
```

And the last one

```bash
emacs /usr/local/hadoop/etc/hadoop/hdfs-site.xml
```

Between `< configuration >`  and `< /configuration >` put this in:

```xml
<property>
<name>dfs.replication</name>
<value>1</value>
<description>Default block replication. The actual number of replications
can be specified when the file is created. The default is used if replication
is not specified in create time.</description>
</property>
```

Also tell hadoop where java 7 is

```bash
emacs /usr/local/hadoop/etc/hadoop/hadoop-env.sh
```

And at the very end, append this line:

```text
export JAVA_HOME=/usr/lib/jvm/java-7-oracle
```

Save, quit, and we're good.


#### Format the HDFS (hadoop filesystem)

```bash
hdfs namenode -format
```

## STOP HERE. Your setup is complete. We'll do the rest together.
