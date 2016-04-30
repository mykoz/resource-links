#PostgreSQL  

[PostgreSQL (Instructions by Ubuntu)](https://help.ubuntu.com/community/PostgreSQL)  
[PostgreSQL (Instructions by Digital Ocean)](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04)  
 * is a powerful object-relational database management system, provided under a flexible BSD-style license  
 * contains many advanced features, is very fast and standards compliant. 

---

### Install PostgreSQL

```bash
$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib
```
This will install _and start up_ Postgres. 

### Searching for 'Postgres'

```bash
$ ps awx | grep post
```

On Ubuntu, servers are started and stopped mostly with [upstart](http://upstart.ubuntu.com/). Try:

```bash
sudo service postgresql status
sudo service postgresql stop
sudo service postgresql start
```
###Logging in as `postgres` user

The installation procedure created a user account called `postgres` that is associated with the default Postgres role. In order to use Postgres, we'll need to log into that account. You can do that by typing:  

```
ubuntu@ip-172-31-61-173:~$ sudo -i -u postgres
postgres@ip-172-31-61-173:~$ 
```
###Create user account on postgres

We want to be able to log in as ourselves. So:

```bash
sudo -u postgres createuser --superuser my_user_name
sudo -u postgres psql
# now in psql...
\password my_user_name
# exit psql...
sudo -u postgres createdb my_user_name
```

Now you can go to town with just `psql`! Explore a little with `help`, `\?`, `\l`, and `\d`.


### Make a database

Check what databases you have so far with `\l`.

You can create a new database with `CREATE DATABASE database_name;`.

Case doesn't matter, but to make it clear what's a SQL word and what's chosen by us I'll follow the ugly SQL convention of capitalizing like a crazy person.

Let's make a database called `endor`.

```sql
CREATE DATABASE endor;
```

Use `\d` to see that there are not yet any tables (relations) in the database. So let's create one.

####Exit out of the PostgreSQL prompt by typing:
```
\q
```

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

Now you can see that you have a table with `\d`. And you can see what's in it like this:

```sql
SELECT * FROM ewoks;
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

