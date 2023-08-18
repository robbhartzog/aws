#### S3 Standard

High Durability (Eleven 9s), high availability (99.99%), can sustain 2 concurrent AZ failures.

_Use Cases_ : Big Data analytics, mobile & gaming applications,content distribution...

#### S3 Standard - Infrequent Access (IA)

S3 Standard - IA (Infrequent Access) offers high durability, throughput, and low latency of  
Amazon S3 Standard, with a low per GB storage price and per GB retrieval fee. Suitable for  
data that is less frequently accessed, but requires rapid access when needed.

_Use Cases_ : As a data store for disaster recovery, backups...

#### S3 One Zone - Infrequent Access

Same as IA but data is stored in a single AZ

_Use Cases_ : Storing secondary backup copies of on-premisedata, or storing data you can  
recreate (e.g. created thumbnails of images)

#### Amazon Glacier

● Low cost object storage meant for archiving / backup  
● Alternative to on-premise magnetic tape storage  
● Cost per storage per month ($0.004 / GB) + retrieval cost  
● **Retrieval options** : Expedited (1 to 5 minutes), Standard(3 to 5 hours), Bulk (5 to 12 hours)  
● Minimum storage duration of 90 days  
● Glacier provides a management console. You can use the **console to create and delete  
vaults**. However, all other interactions with Glacierrequire that **you use the AWS  
Command Line Interface (CLI) or write code**  
● For example, **to upload data** , such as photos, videos,and other documents, you must  
either use the AWS CLI or write code to make requests, using either the REST API directly  
or by using the AWS SDKs  
● Amazon S3 Glacier **automatically encrypts data** at restusing Advanced Encryption  
Standard (AES) 256-bit symmetric keys and supports secure transfer of your data over  
Secure Sockets Layer (SSL).

##### S3 Glacier Vault Lock

**S3 Glacier Vault Lock** allows you to easily deployand enforce compliance controls for  
individual S3 Glacier vaults with a vault lock policy. You can specify controls such as “write once  
read many” (WORM) in a vault lock policy and lock the policy from future edits. Once locked, the  
policy can no longer be changed.

#### Amazon Glacier Deep Archive

● For long term storage – cheaper than Glacier but slower retrieval times  
● Retrieval options: Standard (12 hours), Bulk (48 hours)  
● Minimum storage duration of 180 days

#### S3 Intelligent Tiering

Automatically moves objects between two access tiers based on changing access patterns.  
Small monthly monitoring and auto-tiering fee.

#### S3 Faster Uploads

Multi-Part Upload is recommended as soon as the file is over 100 MB. You can use S3 Transfer  
Acceleration with multipart uploads.