#PostgreSQL  

[PostgreSQL (Instructions by Ubuntu)](https://help.ubuntu.com/community/PostgreSQL)  
[PostgreSQL (Instructions by Digital Ocean)](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04)  
 * is a powerful object-relational database management system, provided under a flexible BSD-style license  
 * contains many advanced features, is very fast and standards compliant

---
## Table of Contents

[A)  Setting up Postgres on Ubuntu](#section-a)  
[B)  Help Commands for Postgres and SQL Database](#section-b)


---

## <a name="section-a"></a>A) Setting up Postgres on Ubuntu

## Setting up

#### Install _and start up_ Postgres

```bash
$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib
```
>my example
```console
ubuntu@ip-172-31-61-173:~$ sudo apt-get install postgresql postgresql-contrib
```

####Check Postgres is installed

```bash
$ ps awx | grep post
```
>my example
```console
ubuntu@ip-172-31-61-173:~$ ps awx | grep post
  839 pts/0    S+     0:00 grep --color=auto post
ubuntu@ip-172-31-61-173:~$ 
```

####Check Postgres is running
>my example
```console
ubuntu@ip-172-31-61-173:~$ ps -C postgres
  PID TTY          TIME CMD
  694 ?        00:00:00 postgres
  696 ?        00:00:00 postgres
  697 ?        00:00:00 postgres
  698 ?        00:00:00 postgres
  699 ?        00:00:00 postgres
  700 ?        00:00:00 postgres
ubuntu@ip-172-31-61-173:~$ 
```

On Ubuntu, servers are started and stopped mostly with [upstart](http://upstart.ubuntu.com/). Try:

```bash
sudo service postgresql status
sudo service postgresql stop
sudo service postgresql start
```
>my example
```console
ubuntu@ip-172-31-61-173:~$ ps -C postgres
  PID TTY          TIME CMD
  694 ?        00:00:00 postgres
  696 ?        00:00:00 postgres
  697 ?        00:00:00 postgres
  698 ?        00:00:00 postgres
  699 ?        00:00:00 postgres
  700 ?        00:00:00 postgres
ubuntu@ip-172-31-61-173:~$ sudo service postgresql status
9.3/main (port 5432): online
ubuntu@ip-172-31-61-173:~$ sudo service postgresql stop
 * Stopping PostgreSQL 9.3 database server                                         [ OK ] 
ubuntu@ip-172-31-61-173:~$ sudo service postgresql status
9.3/main (port 5432): down
ubuntu@ip-172-31-61-173:~$ ps -C postgres
  PID TTY          TIME CMD
ubuntu@ip-172-31-61-173:~$ 
```

####Logging in as `postgres` user

The installation procedure created a user account called `postgres` that is associated with the default Postgres role. In order to use Postgres, we'll need to log into that account. You can do that by typing:  

>my example
```console
ubuntu@ip-172-31-61-173:~$ sudo -i -u postgres
postgres@ip-172-31-61-173:~$ 
```  

####Create user account on postgres

We want to be able to log in as ourselves. So:

```bash
sudo -u postgres createuser --superuser my_user_name
sudo -u postgres psql
# now in psql...
\password my_user_name
# exit psql...
sudo -u postgres createdb my_user_name
```
---
## <a name="section-b"></a>B) Help Commands for Postgres and SQL Database

### Get List of Commands (help) with `\?` and `\help`
>my example
```bash
postgres-# \?
General
  \copyright             show PostgreSQL usage and distribution terms
  \g [FILE] or ;         execute query (and send results to file or |pipe)
  \gset [PREFIX]         execute query and store results in psql variables
  \h [NAME]              help on syntax of SQL commands, * for all commands
  \q                     quit psql
  \watch [SEC]           execute query every SEC seconds
Query Buffer
  \e [FILE] [LINE]       edit the query buffer (or file) with external editor
  \ef [FUNCNAME [LINE]]  edit function definition with external editor
  \p                     show the contents of the query buffer
  \r                     reset (clear) the query buffer
  \s [FILE]              display history or save it to file
  \w FILE                write query buffer to file
:
```  

####Get list of database commands with `\help` 
>my example
```console
postgres-# \help
Available help:
  ABORT                            DEALLOCATE
  ALTER AGGREGATE                  DECLARE
  ALTER COLLATION                  DELETE
  ALTER CONVERSION                 DISCARD
  ALTER DATABASE                   DO
  ALTER DEFAULT PRIVILEGES         DROP AGGREGATE
  ALTER DOMAIN                     DROP CAST
  ALTER EVENT TRIGGER              DROP COLLATION
  ALTER EXTENSION                  DROP CONVERSION
  ALTER FOREIGN DATA WRAPPER       DROP DATABASE
  ALTER FOREIGN TABLE              DROP DOMAIN
  ALTER FUNCTION                   DROP EVENT TRIGGER
  ALTER GROUP                      DROP EXTENSION
  ALTER INDEX                      DROP FOREIGN DATA WRAPPER
  ALTER LANGUAGE                   DROP FOREIGN TABLE
  ALTER LARGE OBJECT               DROP FUNCTION
```

---

####You can get a Postgres prompt immediately by typing `psql`
>my example
```bash
ubuntu@ip-172-31-61-173:~$ sudo -i -u postgres
postgres@ip-172-31-61-173:~$ psql
psql (9.3.12)
Type "help" for help.
postgres=# 
```

####Exit out of the PostgreSQL prompt by typing `\q`
>my example
```console
postgres=# \q
postgres@ip-172-31-61-173:~$ 
```  

####Create a new role (a new user) by typing `createuser --interactive`
>my example
```console
postgres@ip-172-31-61-173:~$ createuser --interactive
Enter name of role to add: rachel
Shall the new role be a superuser? (y/n) y
postgres@ip-172-31-61-173:~$ 
```  

####Check what databases you have so far with `\l`
>my example
```
postgres=# \l
                                  List of databases
   Name    |  Owner   | Encoding |   Collate   |    Ctype    |   Access privileges   
-----------+----------+----------+-------------+-------------+-----------------------
 postgres  | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 template0 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
(3 rows)
postgres=# \d
No relations found.
postgres=# 
```

####Check what relationships (tables) you have so far with `\d`
>my example
```console
postgres-# \d
No relations found.
postgres-# 
```

---
## Create a Database

### Make a database with `CREATE DATABASE database_name;`

(*Not case-sensitive:*  case doesn't matter, but to make it clear what's a SQL word and what's chosen by us I'll follow the ugly SQL convention of capitalizing like a crazy person.)

Let's make a database called `endor`.

```sql
CREATE DATABASE endor;
```
---

### Make a table

We have to specify the schema of our table, with detail about [data types](http://www.postgresql.org/docs/9.3/static/datatype.html). There are a bunch of data types, but a few are used most commonly.

```sql
CREATE TABLE ewoks (
    id SERIAL PRIMARY KEY,
    name TEXT,
    age INT,
    accuracy DOUBLE PRECISION
);
```

>my example
```sql
postgres=# CREATE DATABASE endor;
CREATE DATABASE
postgres=# \d
No relations found.
postgres=# CREATE TABLE ewoks (
postgres(# id SERIAL PRIMARY KEY,
postgres(# name TEXT,
postgres(# age INT,
postgres(# accuracy DOUBLE PRECISION
postgres(# );
CREATE TABLE
postgres=# \d
              List of relations
 Schema |     Name     |   Type   |  Owner   
--------+--------------+----------+----------
 public | ewoks        | table    | postgres
 public | ewoks_id_seq | sequence | postgres
(2 rows)
postgres=# 
```




Now you can see that you have a table with `\d`. And you can see what's in it like this:

```sql
SELECT * FROM ewoks;
```  

>my example
```sql
postgres=# SELECT * FROM ewoks;
 id | name | age | accuracy 
----+------+-----+----------
(0 rows)
postgres=# 
```  

### Manual data loading / removing

You can load data from inside `psql`:

```sql
INSERT INTO ewoks (name, age, accuracy) VALUES ('Wicket', 8, 0.9);
```

Now `SELECT` to see that your data is there.

Run the `INSERT` again to see what happens.

You can also delete:

```sql
DELETE FROM ewoks WHERE id=2;
```

And finally, you can drop a whole table:

```sql
DROP TABLE ewoks;
```


### Loading data from a file

Make the same `ewoks` table again.

Make a file `ewoks.csv`:

```text
ID,name,years,acc
1,Wicket,8,0.9
```

Postgres can handle CSV input. To load it:

```sql
COPY ewoks FROM '/path/to/ewoks.csv' DELIMITER ',' CSV HEADER;
```

Verify success with `SELECT`.

### Working with baseball data.. 

Let's get some data to work with Lahman baseball data..


```bash
wget http://seanlahman.com/files/database/lahman-csv_2014-02-14.zip
sudo apt-get install unzip
mkdir baseballdata
unzip lahman-csv_2014-02-14.zip -d baseballdata
```

(psql)

```sql
CREATE TABLE IF NOT EXISTS AllstarFull (
	playerID varchar(20) NOT NULL,
	yearID int NOT NULL,
	gameNum varchar(20) NOT NULL,
	gameID varchar(12) DEFAULT NULL,
	teamID text DEFAULT NULL,
	lgID text DEFAULT NULL,
	GP varchar(20) DEFAULT NULL,
	startingPos varchar(20) DEFAULT NULL,
	PRIMARY KEY (playerID,yearID,gameNum)
);


COPY AllstarFull FROM '/home/username/baseballdata/AllstarFull.csv' DELIMITER ',' CSV HEADER;


CREATE TABLE IF NOT EXISTS Salaries (
	yearID int NOT NULL,
	teamID varchar(3) NOT NULL,
	lgID varchar(2) NOT NULL,
	playerID varchar(9) NOT NULL,
	salary double precision DEFAULT NULL,
	PRIMARY KEY (yearID,teamID,lgID,playerID)
);

COPY Salaries FROM '/home/username/baseballdata/Salaries.csv' DELIMITER ',' CSV HEADER;


CREATE TABLE IF NOT EXISTS Schools (
	schoolID varchar(15) NOT NULL,
	schoolName varchar(255) DEFAULT NULL,
	schoolCity varchar(55) DEFAULT NULL,
	schoolState varchar(55) DEFAULT NULL,
	schoolNick varchar(55) DEFAULT NULL,
	PRIMARY KEY (schoolID)
);

COPY Schools FROM '/home/username/baseballdata/Schools.csv' DELIMITER ',' CSV HEADER;
```

