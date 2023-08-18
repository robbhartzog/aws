EC2 instances on a private subnet can get access to the internet using NAT instance or NAT  
Gateway. NAT instance is an individual EC2 instance. NAT Gateway is a highly available  
gateway ( **you should always use NAT Gateway in thereal world** ).

When creating a NAT instance, disable Source/Destination check on the instance (because it is  
essentially a pass through).

● NAT instances must be in a public subnet.  
● There must be a route out of a private subnet to NAT instance (so it can access the  
internet). If the NAT instance becomes a bottleneck, increase the instance size.  
● You can create high availability using AutoScaling groups, multiple subnets in different AZs  
and a script to automate failover.  
● NAT instances must be associated with a Security Group.  
● For IPv4 outbound internet traffic from a private subnet, you can use a NAT instance or NAT  
Gateway

#### NAT Gateway

● NAT gateways are automatically assigned public IP address

● NAT gateway is deployed inside a subnet and it can scale only inside that subnet. For fault  
tolerance, **it is recommended that you deploy one NATgateway per Availability Zone**  
● Does not support port forwarding  
● NAT Gateways do not have to be associated with any security group

#### Egress only

● IPv6 uses Egress only Internet Gateway for outbound requests from a private Subnet.
![[Pasted image 20230816214543.png]]
● NAT Gateways cannot span Availability Zones.  
● NAT Gateways are not associated with any Security groups  
● For redundancy, NAT Gateways must be setup in multiple AZs and routing tables must be  
configured so that resources use the NAT Gateway in the same AZ they are in