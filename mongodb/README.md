##MongoDB Notes

###Installing MongoDB on local machine

[Install MongoDB Community Edition on OS X](https://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/)

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

####See how many instances of mongo are running
```bash
reshama$ ps -ax | grep mongo
35526 ??         0:00.80 /usr/local/opt/mongodb/bin/mongod --config /usr/local/etc/mongod.conf
35554 ttys001    0:00.00 grep mongo
reshama$
```

#### shutdown mongo process (other ways to shutdown mongodb - google it)
```bash
reshama$ kill -2 35526
reshama$  
```


