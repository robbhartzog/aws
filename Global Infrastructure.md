## AWS Region

● geographical area such as US East, etc. Has at least two availability zones.

## Availability Zone

● one or more discrete data centers with redundant power, networking, and connectivity in an  
AWS Region  
● AZs within a region provide inexpensive, low-latency network connectivity to other zones in  
the same region. This allows you to replicate your data across data centers in a  
synchronous manner so that failover can be automated and be transparent for your users.

Availability Zone is a logical name, and for each account, it could map to different physical  
locations. This logical name can potentially introduce new failure points when integrating  
applications across accounts. So, for cross-account integration, AWS has introduced a new  
name **Availability Zone ID. This name points to thesame physical location across  
accounts**. When doing cross-account application integration,it is a good practice to check  
availability zone ID.

## Edge Location

● used for caching. Essentially used by CloudFront (Amazon’s CDN - Content Delivery  
Network)

## Local Zone

● Extension of an AWS Region  
● Places AWS compute, storage, database, and other selected AWS services closer to end  
users to run latency-sensitive applications  
● Compatible with EC2, RDS, ECS, EBS, ElastiCache, Direct Connect ...

## WaveLength Zone

● infrastructure deployments embedded within the telecommunications providers’ datacenters  
at the edge of the 5G networks

● Ultra-low latency applications through 5G networks  
● High-bandwidth and secure connection to the parent AWS Region