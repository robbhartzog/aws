● SQS is pull based, not push  
● Messages are 256KB in size  
● Messages can be kept in the queue from 1 minute to 14 days; the **default retention period  
is 4 days**  
● you cannot set a priority to individual items in the SQS queue.

● SQS long polling does not return a response until a message arrives in the queue, reducing  
your overall cost over time. Short polling WILL return empty responses.

**_Delay Queues_** is a period of time during which AmazonSQS keeps new SQS messages  
invisible to consumers. In SQS Delay Queues, a message is hidden when it is first added to the  
queue. (default: 0 mins, **max.: 15 mins** ). Delay queueslet you _postpone the delivery of_ **_all new  
messages_** to a queue.

You can use **_message timers_** to set an initial invisibilityperiod for a message added to a queue.  
So, if you send a message with a 60-second timer, the message isn't visible to consumers for its  
first 60 seconds in the queue. The default (minimum) delay for a message is 0 seconds. The  
maximum is 15 minutes. Therefore, you should use message timers _to postpone the delivery of_  
**_certain_** _messages_ to the queue by one minute.

**_Visibility Timeout_** is a period of time during whichAmazon SQS prevents other consumers  
from receiving and processing the message again. In Visibility Timeout, a message is hidden  
only after it is consumed from the queue. Increasing the Visibility Timeout gives more time to the  
consumer to process the message and prevent duplicate reading of the message. ( **default: 30  
sec** ., min.: 0 sec., **max.: 12 hours** )

**_Dead Letter Queue_** is where other SQS queues (sourcequeues) can send messages that can't  
be processed (consumed) successfully. It's useful for debugging as it allows you to isolate  
problematic messages so you can debug why their processing doesn't succeed.

A single Amazon SQS message queue **can contain an unlimitednumber of messages**.  
Messages are inflight after they have been received from the queue by a consuming  
component, but have not yet been deleted from the queue. However, there is a 120,000 limit for  
the number of inflight messages for a standard queue and 20,000 for a FIFO queue.

#### SQS Standard Queues

● Guarantees that your message will be delivered at least once (occasionally more than once)  
● Can have out of order messages (best effort ordering)

#### SQS FIFO Queues

FIFO (First-In-First-Out) Queues have all the capabilities of the SQS Standard Queue

● Order in which messages are sent and received are strictly preserved  
● Message is delivered once and remains available until a consumer processes and deletes it.  
● Duplicated messages are not introduced into the queue.  
● FIFO queues support up to 300 messages per second (300 send, receive, or delete  
operations per second). When you batch 10 messages per operation (maximum), FIFO  
queues can support up to 3,000 messages per second.

● The name of a FIFO queue must end with the **.fifo** suffix

#### Amazon SQS temporary queues

Temporary queues help you save development time and deployment costs when using common  
message patterns such as request-response. You can use the Temporary Queue Client to  
create high-throughput, cost-effective, application-managed temporary queues.

The client maps multiple temporary queues—application-managed queues created on demand  
for a particular process—onto a single Amazon SQS queue automatically. This allows your  
application to make fewer API calls and have a higher throughput when the traffic to each  
temporary queue is low.