S3 Replication automatically replicates objects across different S3 buckets. Every object  
uploaded to an S3 bucket is automatically replicated to a destination bucket.

It replicates every object-level upload that you directly make to your source bucket. The  
metadata and ACLsassociated with the object are alsopart of the replication.

● Versioning must be enabled on both the source and destination buckets  
● If source and destination buckets are in different regions, it is Cross Region Replication  
(CRR)  
● If source and destination buckets are in the same region, it is Same Region Replication  
(SRR)  
● Files in an existing bucket are not replicated automatically. **By default, replication only  
supports copying new Amazon S3 objects after it is enabled.**  
● Optionally, you can replicate existing objects using **S3 Batch Replication**  
● All subsequent updated files will be replicated automatically  
● Delete markers are not replicated  
● Deleting individual versions or delete markers will not be replicated  
● Replication cannot be chained. If B1 is replicated to B2 and B2 is replicated to B3, an object  
uploaded to B1 will be replicated only to B2. It won’t be replicated to B3.