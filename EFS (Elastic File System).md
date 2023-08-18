● Supports the Network File System version 4 (NFSv4.1) protocol  
● Works only with Linux instances only, not Windows  
● Can be attached to **multiple EC2 instances in differentAZ**

● Use Security Groups to control access to EFS  
● You only pay for the storage you use (no pre-provisioning required)  
● Can scale up to petabytes  
● Can support thousands of concurrent NFS connections  
● Data is stored across multiple AZs within a region  
● Read After Write consistency  
● Use cases: content management, web serving, data sharing,Wordpress

**Bursting Throughput mode**

Throughput on Amazon EFS scales as the size of your file system in the standard storage class  
grows.

**Provisioned Throughput mode**

You can instantly provision the throughput of your file system (in MiB/s) independent of the  
amount of data stored.

**Max I/O performance mode**

Used to scale to higher levels of aggregate throughput and operations per second. This scaling  
is done with a tradeoff of slightly higher latencies for file metadata operations. Highly parallelized  
applications and workloads, such as big data analysis, media processing, and genomic  
analysis, can benefit from this mode.

#### FSx

**Amazon FSx** makes it easy and cost effective to launchand run popular file systems that are  
fully managed by AWS.

#### FSx for Lustre

It is used for workloads such as machine learning, high-performance computing (HPC), video  
processing, and financial modeling.

FSx for Lustre integrates with Amazon S3, making it easy to process data sets with the Lustre  
file system. When linked to an S3 bucket, an FSx for Lustre file system transparently presents  
S3 objects as files and allows you to write changed data back to S3.

**Fargate does not support connection to FSx for Lustre.**

#### FSx for Windows File Server

Provides fully managed, highly reliable file storage that is accessible over the industry-standard  
Service Message Block (SMB) protocol. Built on Windows. Microsoft AD integration. _You can  
easily connect Linux instances to the file system by installing the cifs-utils package. The Linux  
instances can then mount an SMB/CIFS file system._