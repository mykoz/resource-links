Set up secure access

 1. Choose to "Create a new key pair" and give it a nice name.
 2. Download your `.pem` file.
 3. Move your file somewhere sensible like `~/.ssh/`.
 4. Make your file read only with `chmod 400 filename`.
 

```
reshama$ cd ~/.ssh
reshama$ pwd
/Users/reshamashaikh/.ssh
```
filename:
awskey_ds7.pem

```
reshama$ pwd
/Users/reshamashaikh/Downloads
reshama$ ls *.pem
-rw-r--r--@ 1   1692 Apr 10 16:25 awskey_ds7.pem
reshama$ 
reshama$ mv *.pem /Users/reshamashaikh/.ssh
reshama$ 
```

```
reshama$ ls *ds7*
-rw-r--r--@ 1   1692 Apr 10 16:25 awskey_ds7.pem
reshama$ chmod 400 awskey_ds7.pem
reshama$ ls *ds7*
-r--------@ 1   1692 Apr 10 16:25 awskey_ds7.pem
reshama$ 
```

###Billing:  Get notified of estimated charges  
 * Create billing alerts (so you are not surprised when you receive your credit card bill)
 * Select all 3:  
    * Receive PDF Invoice By Email
    * Receive Billing Alerts
    * Receive Billing Reports
 * Save Preferences
 
Back to:  View Instances


 

