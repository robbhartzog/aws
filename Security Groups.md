AWS security groups (SGs) are associated with _EC2instances_ (compute resources?) and  
provide security at the protocol and port access level. Each security group — working much the  
same way as a firewall — contains a set of rules that filter traffic coming into and out of an EC  
instance.

● All inbound traffic is blocked by default.  
● All outbound traffic is allowed  
● Security Group rules can reference IP or other Security Groups  
● Changes to security groups take effect immediately.  
● Security Groups operate at the instance level  
● You can have any number of EC2 instances within a security group  
● You can have multiple security groups attached to EC2 instance  
● Security Groups are Stateful. This simply means that the outbound rules are subject to the  
inbound rules. For example, if you add a rule which allows HTTP (Port 80) inbound, it will  
automatically be allowed outbound.  
● With NACLs (Network Access Control Lists), on the other hand, when you want to allow a  
port, you have to add rules for both inbound and outbound traffic, as NACLs are stateless.  
● Another big difference between the two is that you cannot have deny rules with Security  
Groups; only allow rules. You can add both allow and deny rules with NACLs.  
● Security Groups are applied to ENIs (Network Interfaces), while NACLs are applied to  
subnets  
● **Security Groups cannot be used to block ports or IP addresses**.

Security Groups and VPCs can span availability zones but neither can span regions.

AWS has removed the Firewall appliance from the hub of the network and implemented the  
firewall functionality as stateful Security Groups, and stateless subnet NACLs. This is not a new  
concept in networking, but rarely implemented at this scale. In this case an IAM role by itself will  
not be enough to gain access to the AWS infrastructure - an IAM user will also be required.
![[Pasted image 20230816213849.png]]