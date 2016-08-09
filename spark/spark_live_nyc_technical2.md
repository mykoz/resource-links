

https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/1025105642612129/1239890846175194/4592099822616319/latest.html

####Reading from Disk vs Memory

The 255 MB pageviews file is currently on S3, which means each time you scan through it, your Spark cluster has to read the 255 MB of data remotely over the network.  


