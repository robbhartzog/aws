**Amazon Aurora** is a MySQL and PostgreSQL-compatiblerelational database. It features a  
distributed, fault-tolerant, self-healing storage system that auto-scales up to 128TB per  
database instance. It delivers high performance and availability with up to 15 low-latency read  
replicas, point-in-time recovery, continuous backup to Amazon S3, and replication across 3 AZs.

● Two copies of your data are contained in each AZ, with a minimum of 3 AZ (6 copies of your  
data)  
● 2 types of replicas are available. Aurora replicas and MySQL replicas. Automated failover is  
available with only Aurora replicas  
● **An Aurora Replica is both a standby in a Multi-AZ configuration and a target for read  
traffic**.  
● Aurora has automated backups available and you can also take snapshots. You can share  
snapshots with other AWS accounts.

● For Amazon Aurora, each Read Replica is associated with a priority tier (0-15). In the event  
of a failover, Amazon Aurora will promote the Read Replica that has the highest priority (the  
lowest numbered tier).  
● Amazon Aurora **Global Database** is designed for globallydistributed applications, allowing  
a single Amazon Aurora database to span multiple AWS regions