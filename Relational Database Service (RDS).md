● RDS runs on virtual machines but you cannot access or login into those servers  
● Patching of RDS and underlying OS is Amazon’s responsibility  
● RDS is not serverless (Aurora Serverless is kind of serverless and an exception to this)  
● You are charged for the type and size of the database, the uptime, any additional storage of  
backup (above the DB size), requests, deployment type (e.g. you pay for multi AZ), and data  
transfer outbound.  
● Amazon RDS creates an **SSL certificate** and installsthe certificate on the DB instance  
when Amazon RDS provisions the instance. These certificates are signed by a certificate  
authority. The SSL certificate includes the DB instance endpoint as the Common Name (CN)  
for the SSL certificate to guard against spoofing attacks. You can download a root certificate  
from AWS that works for all Regions or you can download Region-specific intermediate  
certificates.

The following databases are available:

● MySQL  
● PostgreSQL  
● MariaDB  
● Oracle  
● MS SQL server  
● Aurora

When you provision aMulti-AZDB Instance, AmazonRDS **synchronously** replicates the data  
to a standby instance in a different Availability Zone (AZ). Multi-AZ should be used for disaster  
recovery. In case your primary DB goes down, AWS will automatically switch over to DB in  
another AZ. You can force a failover from one AZ to another by rebooting the RDS instance.  
When failing over, Amazon RDS simply flips the canonical name record (CNAME) for your DB  
instance to point at the standby, which is in turn promoted to become the new primary.

Any **database engine level upgrade** for an RDS DB instance with Multi-AZ deployment triggers  
both the **primary and standby DB instances to be upgraded at the same time. This causes  
downtime until the upgrade is complete.**

For Multi-AZ, RDS applies OS updates by performing maintenance on the standby, then  
promoting the standby to primary, and finally performing maintenance on the old primary, which  
becomes the new standby.

With automated backups, I/O activity is no longer suspended on your primary during your  
preferred backup window, since backups are taken from the standby.

A Multi-AZ standby cannot serve read requests.

To improve performance you should use read replicas. **Read replicas can be in another  
region.** Backups must be enabled for read replicas.A read replica is billed as a standard DB  
Instance and at the same rates. You are not charged for the data transfer incurred in replicating  
data between your source DB instance and read replica within the same AWS Region.

You can create a read replica as a Multi-AZ DB instance. Amazon RDS creates a standby of  
your replica in another Availability Zone for failover support for the replica. Creating your read  
replica as a Multi-AZ DB instance is independent of whether the source database is a Multi-AZ  
DB instance.

Read replicas can be promoted to master, but that breaks the read replication.

#### RDS Monitoring

Amazon RDS provides metrics in real time for the operating system (OS) that your DB instance  
runs on. You can view the metrics for your DB instance using the console, or consume the  
Enhanced Monitoring JSON output from CloudWatch Logs in a monitoring system of your  
choice.

Take note that there are certain differences between CloudWatch and Enhanced Monitoring  
Metrics. CloudWatch gathers metrics about CPU utilization from the hypervisor for a DB  
instance, and Enhanced Monitoring gathers its metrics from an agent on the instance. As a  
result, you might find differences between the measurements, because the hypervisor layer  
performs a small amount of work.

#### Automated backups

● Backups are automatically enabled in RDS  
● Automated backups:  
○ Daily full backup of the database (during the maintenance window)

○ Transaction logs are backed-up by RDS every 5 minutes  
○ => ability to restore to any point in time (from oldest backup to 5 minutes ago)  
○ 7 days retention (can be increased to 35 days)  
● DB Snapshots:  
○ Manually triggered by the user  
○ Retention of backup for as long as you want

#### Database snapshots

● Manually triggered by the user  
● Retention of backup for as long as you want. Stored in Amazon S3 that are kept until you  
explicitly delete them.  
● You can create a new instance from a database snapshots whenever you desire

#### RDS Storage Auto Scaling

● Helps you increase storage on your RDS DB instance dynamically  
● When RDS detects you are running out of free database storage, it scales automatically  
● Automatically modify storage if:  
○ Free storage is less than 10% of allocated storage  
○ Low-storage lasts at least 5 minutes  
○ 6 hours have passed since last modification  
● You have to set Maximum Storage Threshold (maximum limit for DB storage)

#### RDS Read Replicas

● Up to 5 Read Replicas  
● Within AZ, Cross AZ or Cross Region  
● **Replication is ASYNC** , so reads are eventually consistent  
● Replicas can be promoted to their own DB  
● Applications must update the connection string to leverage read replicas  
● For RDS Read Replicas within the same region, you don’t pay network cost

#### RDS Multi AZ (Disaster Recovery)

**● SYNC replication**  
● One DNS name – automatic app failover to standby  
● Increase availability  
● Failover in case of loss of AZ, loss of network, instance or storage failure  
● No manual intervention in apps  
● Not used for scaling

● Multi-AZ replication is free  
● Note:The Read Replicas can be setup as Multi AZ for Disaster Recovery (DR)  
● Change from Single-AZ to Multi-AZ can be done with zero downtime

#### RDS Encryption

##### At rest encryption

● Possibility to encrypt the master & read replicas with AWS KMS - AES-256 encryption  
● Encryption has to be defined at launch time  
● If the master is not encrypted, the read replicas cannot be encrypted  
● Transparent Data Encryption (TDE) available for Oracle and SQL Server

##### In-flight encryption

● SSL certificates to encrypt data to RDS in flight  
● Provide SSL options with trust certificate when connecting to database  
● To enforce SSL:  
● PostgreSQL: rds.force_ssl=1 in the AWS RDS Console (Parameter Groups)  
● MySQL: Within the DB:

GRANT USAGE ON _._ TO 'mysqluser'@'%' REQUIRE SSL;

Encryption at rest is supported for all RDS databases. Encryption is done using AWS Key  
Management Service (KMS). Once an RDS instance is encrypted, data stored at rest in  
underlying storage is encrypted, as are its automated backups, read replicas and snapshots.