● Lambda **billing** is based on both: **MB of RAM (memory)reserved and the execution  
duration in 100ms units**.  
● API-Gateway Events, S3 Events and DynamoDB Events are all valid triggers for Lambda  
functions  
● **Lambda@Edge** is a feature of CloudFront that lets yourun code closer to your users, which  
improves performance and reduces latency.  
● Lambda functions always operate from an **AWS-ownedVPC. By default, your function  
has the full ability to make network requests to any public internet address** — this  
includes access to any of the public AWS APIs. For example, your function can interact with  
AWS DynamoDB APIs to PutItem or Query for records. You should only enable your  
functions for VPC access when you need to interact with a private resource located in a  
private subnet. An RDS instance is a good example.  
● Once your function is VPC-enabled, all network traffic from your function is subject to the  
routing rules of your VPC/Subnet. If your function needs to interact with a public resource,  
you will need a route through a NAT gateway in a public subnet.