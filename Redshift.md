● Used for Business Intelligence  
● Available in only one AZ  
● Backup is enabled automatically with 1 day retention by default and 35 day max  
● Attempts to maintain three copies of your data (the original and replica on the compute  
nodes and a backup in Amazon S3)  
● Redshift can also **asynchronously replicate your snapshotsto S3 in another region for  
disaster recovery**

#### Redshift Spectrum

Using Amazon Redshift Spectrum, you can efficiently query and retrieve structured and  
semistructured data from files in Amazon S3 without having to load the data into Amazon  
Redshift tables.  
Amazon Redshift Spectrum resides on dedicated Amazon Redshift servers that are  
independent of your cluster. Redshift Spectrum pushes many compute-intensive tasks, such as  
predicate filtering and aggregation, down to the Redshift Spectrum layer. Thus, Redshift  
Spectrum queries use much less of your cluster's processing capacity than other queries.

#### Enhanced VPC Routing