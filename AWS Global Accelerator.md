AWS Global Accelerator is a service that can direct users to the nearest AWS Region that  
contains an endpoint for an application. The service utilizes Edge locations to decrease latency  
and then forwards all traffic on the AWS global network which also decreases latency.

It improves the availability and performance of applications with local or global users.

It provides static IP addresses that act as a **fixedentry point** to application endpoints in a  
single or **multiple AWS Regions** , such as ApplicationLoad Balancers, Network Load Balancers  
or EC2 instances.

Global Accelerator improves performance for a wide range of applications over TCP or UDP by  
proxying packets at the edge to applications running in one or more AWS Regions. Global  
Accelerator is a good fit for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice  
over IP, as well as for HTTP use cases that specifically require static IP addresses or  
deterministic, fast regional failover.

Global Accelerator uses endpoint weights to determine the proportion of traffic that is directed to  
endpoints in an endpoint group, and traffic dials to control the percentage of traffic that is  
directed to an endpoint group (an AWS region where your application is deployed). **Preferred  
over DNS service for blue/green routing when DNS caching is a problem.**