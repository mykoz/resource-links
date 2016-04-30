##PostgreSQL  

[PostgreSQL (Ubuntu)](https://help.ubuntu.com/community/PostgreSQL)  
[PostgreSQL Instructions (by Digital Ocean)](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04)  
 * is a powerful object-relational database management system, provided under a flexible BSD-style license  
 * contains many advanced features, is very fast and standards compliant. 
 
(schedule w4_d2)
```
ubuntu@ip-172-31-55-178:/home$ #this installs and starts up postgres
ubuntu@ip-172-31-55-178:/home$ ps awx | grep post
```
```
22194 ?        S      0:00 /usr/lib/postgresql/9.3/bin/postgres -D /var/lib/postgresql/9.3/main -c config_file=/etc/postgresql/9.3/main/postgresql.conf
22196 ?        Ss     0:00 postgres: checkpointer process                                                                                              
22197 ?        Ss     0:00 postgres: writer process                                                                                                    
22198 ?        Ss     0:00 postgres: wal writer process                                                                                                
22199 ?        Ss     0:00 postgres: autovacuum launcher process                                                                                       
22200 ?        Ss     0:00 postgres: stats collector process                                                                                           
22288 pts/0    S+     0:00 grep --color=auto post
```
```
ubuntu@ip-172-31-55-178:/home$ sudo service postgresql status
9.3/main (port 5432): online
ubuntu@ip-172-31-55-178:/home$ sudo service postgresql stop
 * Stopping PostgreSQL 9.3 database server                                         [ OK ] 
ubuntu@ip-172-31-55-178:/home$ sudo service postgresql start
 * Starting PostgreSQL 9.3 database server                                         [ OK ] 
ubuntu@ip-172-31-55-178:/home$ 
```

