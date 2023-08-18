ECS Task Role is the IAM Role used by the ECS task itself. Use when your container wants to  
call other AWS services like S3, SQS, etc.

EFS volume can be shared between different EC2 instances and different ECS Tasks. It can be  
used as a persistent multi-AZ shared storage for your containers.

To specify permissions for a specific task on Amazon ECS you should use IAM Roles for Tasks.  
The permissions policy can be applied to tasks when creating the task definition, or by using an  
IAM task role override using the AWS CLI or SDKs. The **_taskRoleArn_** parameter is used to  
specify the policy.

**_AmazonECSTaskExecutionRolePolicy_** policy is the Task Execution IAM Role. This is used by  
the container agent to be able to pull container images, write log files etc.

#### ECS with EC2

#### ECS with AWS Fargate