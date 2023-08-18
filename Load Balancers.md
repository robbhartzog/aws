● Spread load across multiple downstream instances  
● Provide SSL termination (HTTPS) for your websites  
● High availability across zones  
● Enforce stickiness with cookies  
● The following cookie names are reserved by the ELB (AWSALB, AWSALBAPP,  
AWSALBTG).  
● The most secure way of ensuring only the ALB can access the EC2 instances is to add the  
ALB security group to the EC2 security group.

##### Classic Load Balancer

● Classic Load balancer (inexpensive, no builtin intelligence, sends traffic to instance with  
least load)  
● supports the following protocols - HTTP, HTTPS, TCP  
● No IP, just DNS name

##### Application Load Balancer

● Supports Layer 7 HTTP, HTTPS, WebSockets  
● Application load balancer (for intelligent routing)  
● ALBs can route traffic to different Target Groups based on URL Path, Hostname, HTTP  
Headers, and Query Strings.  
● No IP, just DNS name. Cannot assign Elastic IP  
● 504 error means that application is not responding within specified timeout period  
● For HTTP request, If you need an IP address of the user, look for X-Forwarded-For header  
●  Slower than a NLB because it's layer 7 but it can check for application health.

##### Network Load Balancer

● Network load balancer (for high performance routing). It can handle millions of requests per  
second with low-latency.  
● Operates at Layer 4, and is best-suited for load-balancing TCP, UDP, and TLS traffic

● Network Load Balancer has one static IP address per AZ and you can attach an Elastic IP  
address to it.  
● Target Groups can be EC2 instances (including ASG), ECS tasks, Lambda functions or  
private IP addresses. For IP address target type, you can route traffic using any private IP  
address from one or more network interfaces.  
● Health checks are at Target Group level  
● Network Load Balancer **does not currently support securitygroups**.

##### Gateway Load Balancer

● Operates at Layer 3 (Network Layer) – IP Packets  
● Deploy, scale, and manage a fleet of 3rd party network virtual appliances in AWS

#### Sticky Sessions

● Sticky sessions allow you to bind a user’s session to a specific EC2 instance. This ensures  
that all requests from the user during the session are sent to the same instance.

● For Classic LB, requests are sent to the same instance

● For Application LB, sticky sessions can be enabled but the traffic will be sent at target group  
level

#### Cross Zone Load Balancing

● When Cross-Zone Load Balancing is enabled, ELB distributes traffic evenly across all  
registered EC2 instances in all AZs.

● Cross-Zone Load Balancing is enabled for ALB by default. It is disabled for ELB and NLB by  
default. Can be enabled - no extra cost for ELB, charges for NLB

#### Path Patterns

● You can create a listener with rules to route traffic based on the URL path

#### SSL/TLS Certificates

● CLB supports only one SSL certificate. Must use multiple CLB for multiple hostname with  
multiple SSL certificates  
● ALB and NLB support multiple listeners with multiple SSL certificates. Uses Server Name  
Indication (SNI) to make it work. Server Name Indication (SNI) allows you to expose multiple  
HTTPS applications each with its own SSL certificate on the same listener.