Use subnets to define internet accessibility. **A subnetcan only be associated with one route  
table at a time.**

#### Private Subnets

● Do not have a routing table entry to an internet gateway  
● Not directly accessible from the public internet

● To support restricted, outbound-only public internet access, typically use a “jump box” (NAT /  
proxy / bastion host)

#### Public Subnets

When a Subnet is created, it is a private subnet by default. You must set Auto-assign IPv4 to  
true for a public subnet, so EC2 instances created in that subnet can be assigned public IP  
addresses.

By default, the main VPC route table will have only an entry for VPC CIDR so that subnets can  
talk to each other. To support inbound/outbound access to the public internet, you should:

1. create a new route table
2. add a routing table entry to an Internet Gateway for 0.0.0.0:/0 (IPv4) and ::/0 (IPv6)
3. Associate this new route table with the public subnet

**Note** : Do not add routing table entry for IGW to themain route table as this will make all subnets  
in that VPC as public which could be a potential security threat.

Traffic to and from the internet into VPC is routed through the Internet Gateway (IGW). You must  
create an Internet Gateway and attach it to a VPC. Only one IGW can be attached to a VPC.