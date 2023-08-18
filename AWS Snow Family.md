The original Snowball devices were transitioned out of service and Snowball Edge Storage  
Optimized are now the primary devices used for data transfer. You may see the Snowball device  
on the exam, just remember that the original Snowball device had 80TB of storage space.

You can't move data directly from Snowball into a Glacier Vault or a Glacier Deep Archive Vault.  
You need to go through S3 first and then use a lifecycle policy. For this scenario, you will want to  
minimize the time spent in S3 Standard for all files to avoid unintended S3 Standard storage  
charges. To do this, AWS recommends using a zero-day lifecycle policy. From a cost  
perspective, when using a zero-day lifecycle policy, you are only charged S3 Glacier Deep  
Archive rates.

#### Snowcone

AWS Snowcone is a small, portable, rugged, and secure edge computing and data transfer  
device. It provides **up to 8 TB of usable storage**.

#### Snowball Edge

Snowball Edge is best-suited to move **petabytes** ofdata and offers computing capabilities. Be  
careful, it's recommended to use a fleet of Snowballs to move **less than 10PBs** of data. Over  
this quantity, it's better-suited to use Snowmobile.

You can **run Amazon EC2 compute instances hosted ona Snowball Edge** with the sbe1,  
sbe-c, and sbe-g instance types. The sbe1 instance type works on devices with the Snowball  
Edge Storage Optimized option. The sbe-c instance type works on devices with the Snowball  
Edge Compute Optimized option. Both the sbe-c and sbe-g instance types work on devices with  
the Snowball Edge Compute Optimized with GPU option.

#### Snowball Edge Compute Optimized

Snowball Edge Compute Optimized provides powerful computing resources for higher  
performance workloads such as machine learning, full motion video analysis, analytics, and  
local computing stacks. Despite providing local computing capacity, AWS Snowball Edge  
Compute Optimized devices are not best-suited for data transfer, but instead the high  
performance workloads mentioned above.

#### Snowball Edge Storage Optimized

Snowball Edge Storage Optimized devices are well suited for large-scale data migrations and  
recurring transfer workflows, as well as local computing with higher capacity needs.

#### Snowmobile

Snowmobile is used to move exabytes of data in or out of AWS (1 EB=1,000 PBs=1,000,000  
TBs).