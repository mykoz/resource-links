#Amazon Web Services 
##Setting up Cloud Computing :cloud:

1.  Log in  
  http://aws.amazon.com/  
  (Note:  put your user id and password somewhere for easy reference)

2.  [AWS Free Tier](https://aws.amazon.com/free/)  
  * credit card required for log-in
  * designed to enable you to get hands-on experience with AWS Cloud Services
  * includes services with a free tier available for 12 months following your AWS sign-up date, as well as additional service offers that do not automatically expire at the end of your 12 month AWS Free Tier term.

3.  AWS Console  
  Lot of options!  We will choose "Compute/EC2"  [upper left of screen]  
  EC2 = Elastic Compute Cloud    
  ![AWS Console](img/aws_console.png)

4.  Region [on upper right of screen]  
  Select:  US East (N. Virginia)

5.  Create Instance
    From your EC2 Dashboard, click the blue "Launch Instance" button.

---
##Setting up Instance

Step 1) Choose an Amazon Machine Image (AMI):  Ubuntu Server [press blue Select button]  
Step 2) Choose an Instance Type:  Select a "Free tier eligible" "t2.micro" instance  
Step 3) Configure Instance Details:  [accept default]  
Step 4) Add Storage:  [accept default]  
Step 5) Tag Instance: `awsds7`  
Step 6) Configure Security Group: Name a new security group and allow some more ports if you like. 80 is a fun port to allow.  
>    Add Rule:  select 'Custom TCP Rule'  
    Port Range: 80  
    Review and Launch / Launch    
    
Step 7) Review Instance Launch: your set-up will look like below screenshot  

  ![review instance](img/aws_review_instance.png)
    
    
---

##Connecting to your Instance  
**Save a screen shot:  this pop-up has very valuable information!**

To access your instance:

    Open an SSH client. (find out how to connect using PuTTY)
    Locate your private key file (awskey_ds7.pem). The wizard automatically detects the key you used to launch the instance.
    Your key must not be publicly viewable for SSH to work. Use this command if needed:

    chmod 400 awskey_ds7.pem

    Connect to your instance using its Public DNS:

    ec2-54-152-105-0.compute-1.amazonaws.com

Example:

    ssh -i "awskey_ds7.pem" ubuntu@ec2-54-152-105-0.compute-1.amazonaws.com



Please note that in most cases the username above will be correct, however please ensure that you read your AMI usage instructions to ensure that the AMI owner has not changed the default AMI username.
If you need any assistance connecting to your instance, please see our connection documentation.




 ![connect to instance](img/aws_connect_to_instance.png)


```
reshama$ ssh -i "awskeyds7.pem" ubuntu@ec2-52-90-175-82.compute-1.amazonaws.com

    The authenticity of host 'ec2-52-90-175-82.compute-1.amazonaws.com (52.90.175.82)' can't be established.
ECDSA key fingerprint is SHA256:nxfp+WXpqy4YtZYL+Swe7333bgcHcdF9p8cfpdk+ghM.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'ec2-52-90-175-82.compute-1.amazonaws.com,52.90.175.82' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 14.04.3 LTS (GNU/Linux 3.13.0-74-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Apr 10 21:15:44 UTC 2016

  System load: 0.16             Memory usage: 5%   Processes:       82
  Usage of /:  9.9% of 7.74GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ubuntu@ip-172-31-59-73:~$ 
```
