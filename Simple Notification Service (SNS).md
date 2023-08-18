● Provides instantaneous, push based delivery  
● Flexible message delivery over multiple transport protocols (iOS, Android, text message,  
email, SQL etc.)  
● Kinesis Data Firehose is now supported as a subscriber, but not Kinesis Data Streams.  
● SNS FIFO topic can only have an SQS FIFO queue as a subscriber.

#### SNS + SQS Fanout Pattern

This is a common pattern where only one message is sent to the SNS topic and then "fan-out"  
to multiple SQS queues. This approach has the following features: it's fully decoupled, no data  
loss, and you have the ability to add more SQS queues (more applications) over time.
![[Pasted image 20230816214740.png]]
By default, an Amazon SNS topic subscriber receives every message published to the topic.  
You can use Amazon SNS message filtering to assign a filter policy to the topic subscription,  
and the subscriber will only receive a message that they are interested in. Using Amazon SNS

and Amazon SQS together, messages can be delivered to applications that require immediate  
notification of an event. This method is known as fanout to Amazon SQS queues.