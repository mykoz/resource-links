##MongoDB Notes

###[Installing MongoDB Community Edition](https://docs.mongodb.com/manual/installation/) on local machine
 * [Install on OS X](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/)
 * [Install on Windows](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)
 * [Install on Linux](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

```
$ brew update
$ brew install mongodb
```

---

###Run MongoDB

####Start MongoDB
```bash
reshama$ mongod
```
or
```bash
reshama$ brew services start mongodb
```

####See how many instances of Mongo are running
```bash
reshama$ ps -ax | grep mongo
35526 ??         0:00.80 /usr/local/opt/mongodb/bin/mongod --config /usr/local/etc/mongod.conf
35554 ttys001    0:00.00 grep mongo
reshama$
```

####Shut down MongoDB process (other ways to shut down - google it)
```bash
reshama$ kill -2 35526
reshama$  
```


