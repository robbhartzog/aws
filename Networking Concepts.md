#### Private Address Space

The following IP addresses are reserved for private networks and are visible only inside that  
private network.

**10.0.0.0 - 10.255.255 255.255 (10.0.0.0/8 prefix)**

**172.16.0.0 - 172.31.255.255 (172.16.0.0/12 prefix)**

**192.168.0.0 - 192.168.255.255 (192.168.0.0/16 prefix)**

#### CIDR - Classless inter-domain routing

Sitehttp://CIDR.xyzhas an interactive IP addressand CIDR Range Visualizer.
![[Pasted image 20230816214408.png]]![[Pasted image 20230816214417.png]]![[Pasted image 20230816214429.png]]

#### VPC

Virtual Private Cloud (VPC) lets you provision a logically isolated section of AWS where you can  
launch resources in a virtual network you define. You have complete control and can select your  
IP address range, create subnets, configure route tables and network gateways.

If you have an existing VPC that supports IPv4 only and resources in your subnet that are  
configured to use IPv4 only, you can enable IPv6 support for your VPC and resources. Your  
VPC can operate in dual-stack mode — your resources can communicate over IPv4, or IPv6, or  
both. IPv4 and IPv6 communication are independent of each other. You cannot disable IPv4  
support for your VPC and subnets since this is the default IP addressing system for Amazon  
VPC and Amazon EC2.

Organization: Subnets

Security: Security groups/access control lists

Network isolation: Internet gateways / virtual private gateways / NAT gateways

Traffic direction: Routes
![[Pasted image 20230816214447.png]]

● A single VPC cannot stretch over more than one Availability Zone. However, you have have  
multiple VPCs in one Availability Zone.  
● Security Groups do not span VPCs  
● Only one Internet Gateway can be attached to a VPC.  
● Amazon reserves 5 IP addresses for special purposes (first 4 and last 1)  
● When you create a new VPC, it creates a default Route Table, Network Access Control List  
(NACL) and a default Security Group. It does not create subnets or Internet Gateway

By default VPC that AWS creates is assigned a CIDR block of **172.31.0.0/16**

When a new VPC is created, it looks as shown below.
![[Pasted image 20230816214503.png]]
When you add subnets, this is how it looks:![[Pasted image 20230816214509.png]]