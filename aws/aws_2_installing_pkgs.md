#AWS - Setting up your machine
##Let's start installing packages!

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
---
##Some Helpful Notes

####We can run things as root by prefixing our commands with `sudo`
####To update your libraries
```
ubuntu@ip-172-31-60-68:~$ sudo apt-get update
```
####[`apt-get` Package Management Tool](https://help.ubuntu.com/12.04/serverguide/apt-get.html) 


---

####Install `pip` 
Accept all the suggestions it makes, and hit `Enter` and watch it go.  It will take some time for this to finish installing.    
```
ubuntu@ip-172-31-60-68:~$ sudo apt-get install python-pip
```  
> Fun Fact:  Did you know that when you see a yes/no prompt in this format `[Y]/n`, that you can simply hit `Enter` and it will assume you mean the default(capital and bracketed) option?  No need to type a capital Y.  (time saved can be spent on other things.)  
For `apt-get`, you can alsojust add the `-y` flag.  


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

