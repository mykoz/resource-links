##AWS - Setting up your machine
###Let's start installing packages!

####Check which version of python is installed
```
ubuntu@ip-172-31-60-68:~$ python --version
Python 2.7.6
ubuntu@ip-172-31-60-68:~$ 
```
####Let's use `pip list` to see which packages are installed
```
ubuntu@ip-172-31-60-68:~$ pip list
The program 'pip' is currently not installed. You can install it by typing:
sudo apt-get install python-pip
```
####We can run things as root by prefixing our commands with `sudo`
####To update your libraries
```
ubuntu@ip-172-31-60-68:~$ sudo apt-get update
```
####Install `pip`
```
ubuntu@ip-172-31-60-68:~$ sudo apt-get install python-pip
```

####Add user
```
ubuntu@ip-172-31-60-68:/home$ sudo adduser reshama
```
Note:  pick a password (save it in a place); enter through name fields, etc.


```
ubuntu@ip-172-31-60-68:/home$ cd ..
ubuntu@ip-172-31-60-68:/home$ pwd
/home
ubuntu@ip-172-31-60-68:/home$ ls
reshama  ubuntu
ubuntu@ip-172-31-60-68:/home$ 
ubuntu@ip-172-31-60-68:/home$ cd ubuntu/
ubuntu@ip-172-31-60-68:~$ ls
ubuntu@ip-172-31-60-68:~$ pwd
/home/ubuntu
ubuntu@ip-172-31-60-68:~$ 
```

