#### Kinesis Data Streams

● Capture, process, and store data streams  
● Ingest real-time data such as: Application logs, Metrics, Website clickstreams, IoT telemetry  
data  
● The capacity limits of a Kinesis data stream are defined by the number of shards within the  
data stream. The limits can be exceeded by either data throughput or the number of reading  
data calls. Each shard allows for 1 MB/s incoming data and 2 MB/s outgoing data. You  
should increase the number of shards within your data stream to provide enough capacity.  
● we can only have as many consumers as shards in Kinesis  
● **Cannot** directly write the output to S3 and **does not** offer easy integration with Lambda

Kinesis Data Stream uses the _partition key_ associatedwith each data record to determine which  
shard a given data record belongs to. When you use the identity of each user as the partition  
key, this ensures the data for each user is ordered hence sent to the same shard.

When a host needs to send many records per second (RPS) to Amazon Kinesis, simply calling  
the basic PutRecord API action in a loop is inadequate. To reduce overhead and increase  
throughput, the application must batch records and implement parallel HTTP requests. This will  
increase the efficiency overall and ensure you are optimally using the shards.

The throughput of an Amazon Kinesis data stream is designed to scale without limits via  
increasing the number of shards within a data stream. **Kinesis cannot scale infinitely**.

#### Kinesis Data Firehose

Easiest way to load streaming data into data stores and analytics tools. It can capture,  
transform, and load streaming data into Amazon S3, Amazon Redshift, Amazon Elasticsearch  
Service, API Gateway, Splunk and HTTP endpoint partners. **Cannot load data into  
DynamoDB or EMR**
![[Pasted image 20230816214759.png]]
#### Kinesis Data Analytics

Analyze streaming data in real-time with SQL or Apache Flink. Kinesis Data Analytics cannot  
directly ingest data from the source as it ingests data either from Kinesis Data Streams or  
Kinesis Data Firehose