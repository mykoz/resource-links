##AWS Pop Up Loft
###Getting Started with AWS - Technical Bootcamp

https://events-aws.qwiklab.com/live  

Technical Trainer with AWS:  mattlupo at amazon dot com

name, level of experience, last item bought on Amazon  

new ML 3-day class coming from AWS  

####What is Cloud Computing?
* Utility Service:  on-demand delivery of IT resources over wide network with pay as you go pricing.
    * you pay for what you use
    * you have the option to turn it off
    * in past, bought a server, paid thousands for it up front, and then stuck with that server (no capital expenditure)
         * it is up in minutes; don't have to wait for delivery of hardware; variable expense
    * true elastic capacity:  scale up and down
         * can change from nano to micro instance (can grow resources, they are elastic)
    * improved time to market

####AWS Core Infrastructure Services
Service Offerings:  
* Security Groups
   * firewall
   * can allow or deny traffic to a source
* NACLS (network access control lists)
   * By default, it allows all inbound and outbound traffic
* IAM (identity access management)
   * ability to provision a permission capability
   * user, group, role

Responsibility of the customer is to understand the network components.  
####Network
* VPC (virtual private cloud)
  * segmenting and isolating the equipment from each other
* ELB (elastic load balancer)
  * distribute traffic among multiple nodes in the group
* Route 53
   * 

####Servers --> EC2 (elastic compute cloud)
dealing with virtual servers and compute instances  
* AMI (amazon machine image)
   * contains all the data to put on EC2 instance
   
* 
* Instances

####Storage
* Ephemereal
   * block storage, instance storage
* EBS
   * network attached storage
* S3
   * object storage
* RDS
   * relational database service
* EFS
   * elastic file system

Traditional environment:  servers, hosting centers, data centers  
AWS:  benefits - can go global in seconds; have already established fibers  
* physical facilities make up Amazon global services
* AWS has 13 regions, world-wide, with 4 more coming online
* Region: grouping of at least 2 data zones
* High availability: can create a system that has ability to have failure at primary level, roll over to secondary, and have an acceptable level of downtime

####Edge Locations  
used for storing content; ex:  users upload videos to a site; say one goes viral; store copy of video in 54 locations around the world and direct traffic to that  

####Monitoring Your Cloud Infrastructure
* CloudWatch
   * monitor specific metric of your resources. ex:  CPU of instance ; physical layer, CPU stuff;  Amazon does not have access to your guest level; can see from hardware level or below

####AWS Platform
Customers have difficulty staying on top of all the new platform offerings.  

####Amazon EC2 Overview
Broad set of Compute Instance Types  
* General purpose:  server, balanced server, T2, M3, M4; t-series is a family (t=tiny or temporary); m-series (medium, 2 CPUs 2 GB, balanced)
* Compute optimized: has high compute performance (C3, C4 c=compute; high compute workload, use c-box; C3 is older than C4)
* Storage and IO optimized:   I2, D2 (d=dense storage); 
* GPU enabled; G2
* Memory optimized (R3; rseries; 
* X1's : big storage

####EC2 Terminology
* AMI (amazon machine image); operating system; has all the information it. AMI can be applied to your virtual machine (instance)
* running or stopped (stopped same as shutdown)
* you choose the region, based on factors:  governance, requirements, latency to units, pricing varies by region; different regions have different pricing.  you select regions and availability zone
* need to create VPC (virtual private cloud); all EC2 instances will be launched in VPC (new architecture, old was EC classic)
* launch instance, then attach storage volumes; when you block box, ephemereal storage gone
* EBS (elastic block storage)
* snapshot - point in time back up; grab all the blocks in my availability zone, and put them up in regional level storage, called S3; S3 makes at least 3 copies of your data; your EBS volume is x? specific; higher durability and higher availability  
* there is a snapshot fee; EBS volumes used for constant read and write

####Default VPC
* convenience of pre-built VPC
* automatically assigned network and subnets
* any instances launched 
* security group:  instance based firewall
* direct connect:  least line approach from my location to amazon co-location facility; have port to connect

####Route 53:  going from amazon.com to a fun IP address
* managed DNS service
* domain name registration
* fast zone updates
* Multiple DNS routing features
   * geo based routing
   * latency based routing
   * weighted round robin (
   * DNS failover (my primary record isn't working; ability to health check on records..)
* Zone Apex integration
   * ELB, S3, CloudFront
* Private DNS within VPC
   * internal DNS names not exposed to internet
   * supports split-horizon DNS

####EC2 Pricing Options
* amazon helps you save money
* on-demand; low hourly fee
* good for development testing
* Reserved Instances
   * need box for 1 to 3 years
   * need reserved instance, get cost reduction
   * ex:  reserve M4 large, about 28% reduction
* Spot Instances
   * amazon likes to gamble (annual conf in Las Vegas)
   * allows you to bid on unused instances
   * on-demand prices could get expensive; lower pricing
   * can run spot instance, but could be terminated if someone needs the space
   
####Service-Specific Credentials
* Amazon EC2 key pairs; use key pair to authenticate yourself to the box
   * Public Half:  inserted by Amazon into each Amazon EC2 instance that you launch
   * Private Half:  downloaded to your desktop
* Standard SSH
* Linux launch (first boot)
   * public key made available through metadata
   * public key inserted into `~/.ssh/authorized_keys`
   * user connects with SSH using their private key
   * 
   
####Instance Metadata
http://169.254.169.254/latest/meta-data contains a wealth of info  

####AWS Simply Monthly Calculator
http://calculator.s3.amazonaws.com/index.html
You're not paying for processing power, you're paying for whether the instance is on or off.  

##Storage

####Amazon Simple Storage Service (S3)

####Amazon Glacier
* 1cent/GB/Month
* Integrated with S3

* store all your static files over on S3
* 
####Amazon CloudFront

EMR (elastic map reduce) - managed version of Hadoop

####Structured Data Stores
* DIY on EC2
   * self-managed

* AWS Managed
   * RDMS - Amazon RDS
      * fully managed relational DB service (SQL, MySQL, Oracle, Aurora, postgres, MariaDB)
   * NoSQL - Amazon DynamoDB
   * In-memory Cache - Amazon ElastiCache
   * Data Warehouse - Amazon Redshift (data warehousing)

RDS more expensive  
