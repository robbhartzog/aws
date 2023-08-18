There are three types of Placement Groups.

The name you specify for a placement group must be unique within your AWS account.

You cannot merge placement groups.

You cannot move an existing instance into a placement group. You can create an AMI from your  
existing instance and then launch a new instance from the AMI into a placement group.

Only certain types of instances can be launched in a placement group (Compute Optimized,  
GPU, Memory Optimized, Storage Optimized)
![[Pasted image 20230816213942.png]]
##### Clustered Placement Group

● For Low Network Latency/ High Network Throughput  
● All instances in the same AZ (cannot span multiple AZs)  
● AWS recommends homogeneous instances within clustered placement groups

##### Spread Placement Group
![[Pasted image 20230816213954.png]]
● For Individual Critical EC2 instances  
● EC2 Instances are on different physical hardware  
● Instances can span multiple AZ  
● you can only have amax of 7 running instancesperAZ  
● Use case: Critical Applications where each instance must be isolated from failure from each  
other

##### Partitioned Placement Group
![[Pasted image 20230816214005.png]]
● Up to 7 partitions per AZ  
● instances in a partition do not share racks with the instances in the other partitions  
● Can span across multiple AZs in the same region  
● Up to 100s of EC2 instances  
● EC2 instances get access to the partition information as metadata  
● Use cases: HDFS, HBase, Cassandra, Kafka