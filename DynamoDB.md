● Amazon’s NoSQL database (key-value, document-type)  
● Stored on SSD  
● Spread across 3 geographically distinct data centers  
● Eventually consistent reads (default) - one second rule (app reads data more than 1 second  
after it is written)  
● Strongly consistent reads (application reads data less than one second after it is written)  
● DynamoDB allows for the storage of large text and binary objects, but there is a limit of 400  
KB (combined name and value).  
● Use TTL in DynamoDB to delete old data

There will always be a charge for provisioning read and write capacity and the storage of data  
within DynamoDB, therefore these two answers are correct. There is no charge for the transfer  
of data into DynamoDB, providing you stay within a single region (if you cross regions, you will  
be charged at both ends of the transfer.) There is no charge for the actual number of tables you  
can create in DynamoDB, providing the RCU and WCU are set to 0, however in practice you  
cannot set this to anything less than 1 so there will always be a nominal fee associated with  
each table.

DynamoDB is serverless with no servers to provision, patch, or manage and no software to  
install, maintain or operate. It automatically scales tables up and down to adjust for capacity and  
maintain performance. It provides both provisioned (specify _RCU & WCU_ ) and on-demand (pay  
for what you use) capacity modes.

**Capacity Reservation** allows you to obtain discountson DynamoDB **provisioned throughput  
capacity**. This requires 1 year or 3 year commitmentand **applies for a region** for which the  
capacity was purchased.

Point-in-time recovery (PITR) provides continuous backups of your DynamoDB table data.  
When enabled, DynamoDB maintains incremental backups of your table for the last 35 days

until you explicitly turn it off. **It is a customer responsibility to enable PITR on and AWS is  
responsible for actually performing the backups.**

**DynamoDB Streams** allows you to capture a time-orderedsequence of item-level modifications  
in a DynamoDB table. It's integrated with AWS Lambda so that you create triggers that  
automatically respond to events in real-time.

DynamoDB Streams enable DynamoDB to get a changelog and use that changelog to replicate  
data across replica tables in other AWS Regions.

#### DynamoDB Accelerator (DAX)

DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache for  
DynamoDB that delivers up to 10x performance improvement. It caches the most frequently  
used data, thus offloading the heavy reads on hot keys off your DynamoDB table, hence  
preventing the "ProvisionedThroughputExceededException" exception.