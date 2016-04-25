##Setting up AWS Machine
###Installing Packages

[(w4_d2)](https://github.com/thisismetis/nyc16_ds6/blob/master/04-mcnulty1/02-logistic_sql_load/setting_up_cloud_servers.md)

```
ubuntu@ip-172-31-59-73:/home$ history
    1  clear
    2  pwd
    3  #check if python is installed
    4  python --version
    5  #get into interactive python
    6  python
    7  pwd
    8  cd ..
    9  pwd
   10  ls
   11  #this shows users
   12  ls
   13  #update packages
   14  sudo apt-get upgrade
   15  #install python with anaconda
   16  sudo pip install conda
   17  #install pip
   18  apt-get install pip
   19  #need to be sudo (root)
   20  sudo apt-get install pip
   21  #before you 'apt-search', update our libraries by typing 'sudo apt-get update'
   22  sudo apt-get update
   23  history
   24  apt search pip
   25  sudo apt-get install python-pip
   26  sudo apt-get install python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy
   27  sudo apt-get install git emacs
   28  #create user acct for yourself
   29  sudo adduser reshama
   30  ls
   31  sudo visudo
   32  history
   33  ls
   34  sudo mkdir /home/reshama/.ssh/
   35  sudo nano /home/reshama/.ssh/authorized_keys
   36  history
   
ubuntu@ip-172-31-59-73:/home$ 

```

###AWS:  adduser reshama
```
reshama$ pwd
/Users/reshamashaikh/.ssh
reshama$ ls *ds7*
-r--------@ 1   1692 Apr 10 17:14 awskeyds7.pem
reshama$ #copy this public key to aws .ssh/authorized_keys
reshama$ ls
total 112
-r--------@ 1   1692 Apr 10 17:14 awskeyds7.pem
reshama$ emacs *ds7*

[1]+  Stopped                 emacs *ds7*
reshama$ 
```

```
reshama$ pwd
/Users/reshamashaikh/.ssh
reshama$ emacs id_rsa.pub
```


```
ubuntu@ip-172-31-55-178:/home/reshama/.ssh$ sudo nano authorized_keys
```

Copy in your public key, save, and quit.

Don't log out until you verify that this has worked! Open a new shell on your local machine. You should be able to log in to your remote machine like this:

```
ssh my_cool_username@123.234.123.234
```

Nobody wants to type all that. Edit your `~/.ssh/config`:

```
Host my_cool_machine
Hostname 123.234.123.234
User my_cool_username
```

Now you can log in to your remote machine with `ssh my_cool_machine`.

**Note:  if you get an error, turn off your computer's firewall**  
Apple / System Preferences / Security & Privacy / Firewall

Public DNS
ec2-54-152-1-230.compute-1.amazonaws.com
	
Public IP
54.152.1.230

```
#if this is not working
ssh -i "awskey2ds7.pem" ubuntu@ec2-54-152-1-230.compute-1.amazonaws.com
```

```
$ #using Public ID
$ ssh -i ~/.ssh/awskey2ds7.pem ubuntu@54.152.1.230
```
