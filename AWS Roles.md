● Roles are more secure than storing your access key and secret access key on individual  
EC2 instances  
● Roles are easier to manage  
● Roles can be assigned to an EC2 instance after it is created using both the console and  
command line  
● Roles are universal - you can use them in any region

**AWS Groups** are the standard **groups** which you can consideras collection **of** several users  
and a user can belong to multiple **groups**. A **role is** a set **of** permissions that are assigned to  
an **AWS** entity, such as an EC2 instance, so they canperform tasks that users would not  
normally be allowed to do.

You can create role when you want for e.g. your EC2 instance to be able to access S3 or  
Lambda function.
![[Pasted image 20230816214842.png]]![[Pasted image 20230816214854.png]]![[Pasted image 20230816214905.png]]![[Pasted image 20230816214913.png]]