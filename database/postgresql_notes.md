##Misc Postgres Notes


####Check to see if PostgreSQL is running
```
ubuntu@ip-172-31-61-173:~$ ps -C postgres
  PID TTY          TIME CMD
27357 ?        00:00:00 postgres
27359 ?        00:00:00 postgres
27360 ?        00:00:00 postgres
27361 ?        00:00:00 postgres
27362 ?        00:00:00 postgres
27363 ?        00:00:00 postgres
ubuntu@ip-172-31-61-173:~$ 
```

####Kills all procs running as `postgres`
```bash
ubuntu@ip-172-31-61-173:~$ sudo pkill -u postgres
ubuntu@ip-172-31-61-173:~$ ps -C postgres
  PID TTY          TIME CMD
ubuntu@ip-172-31-61-173:~$ 
```


