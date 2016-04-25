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
####To update your libraries, use `apt-get update`
```
ubuntu@ip-172-31-60-68:~$ sudo apt-get update
```
####[`apt-get` Package Management Tool](https://help.ubuntu.com/12.04/serverguide/apt-get.html)   
Read more about `apt-get` at above link.  


---

####Install `pip` 
Accept all the suggestions it makes, and hit `Enter` and watch it go.  It will take some time for this to finish installing.    
```
ubuntu@ip-172-31-60-68:~$ sudo apt-get install python-pip
```  
> Fun Fact:  Did you know that when you see a yes/no prompt in this format `[Y]/n`, that you can simply hit `Enter` and it will assume you mean the default(capital and bracketed) option?  No need to type a capital Y.  (time saved can be spent on other things.)  
For `apt-get`, you can alsojust add the `-y` flag.  

####Install `scipy` stack
Now that we're on Ubuntu, we can install our stack of usual tools with this line. (There are convenient `apt-get` packages instead of doing everything via `pip`.)
```
sudo apt-get install python-numpy python-scipy python-matplotlib ipython ipython-notebook python-pandas python-sympy python-nose
```

####Install `emacs` editor
We'll also be interacting with repositories from our server, and I like Emacs, so let's do this.  
```
sudo apt-get install git emacs
```

---

####Add user
```
ubuntu@ip-172-31-60-68:/home$ sudo adduser reshama
```
Note:  pick a password (save it in a place); enter through all the other questions (name fields, etc.)  

####User privileges  
Make yourself special by granting yourself root privileges: type `sudo visudo`. This will open up _nano_ (a text editor) to edit the sudoers file. Find the line that says `root    ALL=(ALL:ALL) ALL`. Give yourself a line beneath that which says `[username] ALL=(ALL:ALL) ALL`. Save by hitting Ctrl-o and then Enter when asked for the file name. Exit _nano_ with Ctrl-x.



---

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

