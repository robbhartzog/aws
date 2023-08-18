There are a number of ways to set up a VPN. Based on the options provided, AWS has a  
standard solution that makes use of a VPC with a private subnet, Hardware VPN Access,  
Virtual Private Gateway (VPG), and an on-premise Customer Gateway.

When connecting a VPN between AWS and a third party site, the Customer Gateway is created  
within AWS, but it contains **information about thethird party site e.g. the external IP  
address** and type of routing. The Virtual Private Gatewayhas the information regarding the  
AWS side of the VPN and connects a specified VPC (single VPC) to the VPN. "Direct Connect  
Gateway" and "Cross Connect" are both Direct Connect related terminology and have nothing to  
do with VPNs.
![[Pasted image 20230816214723.png]]

**_Which of these options would you use to provide private connectivity between the  
on-premises data center and AWS cloud? The expected traffic is very low._**

Site-to-Site VPN would meet this requirement, and traffic is routed over the internet. Client VPN  
provides remote connectivity to AWS from any location (for example, from the employee home).  
Direct Connect is used to connect your on-premises data center to AWS cloud and provide  
consistent network performance at high throughput.

**_How would you increase the availability of your VPN setup between on-premises and  
AWS cloud?_**

Use a single virtual private gateway (VGW) and two customer gateways (CGW). VGWs are  
highly available and can tolerate AZ failure. To improve availability on the customer network,  
you need to provision two customer gateways – preferably in different data centers to absorb  
device or data center failures