● Your VPC comes with a default Network ACL (NACL) and by default it allows all inbound  
and outbound traffic  
● Custom NACL denies all inbound and outbound traffic by default  
● Each subnet in your VPC must be associated with an ACL. If you do not explicitly associate  
it with a custom ACL, the subnet is automatically associated with default ACL

● A subnet can be associated with only one ACL at any given time. However, an ACL can  
have many subnets associated with it  
● NACL has a numbered list of rules. These rules are evaluated in ascending order of rule  
number.

###### You need to allow remote SSH login to the private EC2 instances from the

###### on-premises network. All requests are sent over the internet.

**Using the Session Manager (part of the system manager service), authorized employees  
can log in to their EC2 instances using IAM credentials. Session Manager does not use  
SSH or RDP ports.** Bastion Host is another option –however, this requires additional servers,  
and you need to keep the SSH port open. Elastic IP or Public IP for private instances is not  
going to help here as you still need to make the subnet public for access over the internet.

**When a client connects to a server, a random port from the ephemeral port range  
(1024-65535) becomes the client's source port. The designated ephemeral port then  
becomes the destination port for return traffic from the service, so outbound traffic from  
the ephemeral port must be allowed in the network ACL.**

VPC Flow Logs can be created at the VPC, subnet, and network interface levels.