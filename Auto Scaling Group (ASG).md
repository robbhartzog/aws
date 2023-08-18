● Scale out (add EC2 instances) to match an increased load  
● Scale in (remove EC2 instances) to match a decreased load  
● Ensure we have a minimum and a maximum number of machines running  
● Automatically Register new instances to a load balancer  
● ASGs are free. You pay for the underlying resources being launched  
● EC2 instances can be launchedwithin a VPC acrossmultiple AZs. Itcannot launch  
resources into another AWS Region.  
● ASG tries the balance the number of instances across AZ by default  
● IAM roles attached to an ASG will get assigned to EC2 instances

Amazon CloudWatch stores metrics for terminated Amazon EC2 instances or deleted Elastic  
Load Balancers for 2 weeks.

#### Dynamic Scaling Policies

Scaling policies can be on CPU, Network... and can even be on custom metrics or based on a  
schedule (if you know your visitors patterns). Specifies how much to scale in or scale out. One  
or more may be attached to ASG.

##### Manual Scaling

##### Target Tracking Scaling

Most simple and easy to set-up. Example: I want the average ASG CPU to stay at around 40%

##### Simple

```
Increase or decrease the current capacity of the group based on a single scaling adjustment.
```

##### Step Scaling

Increase or decrease the current capacity of the group based on a **set of scaling adjustments** ,  
known as **step** adjustments, that vary based on thesize of the alarm breach. For e.g. when a  
CloudWatch alarm is triggered for:

1. CPU Utilization between 50% and 60%, then add 1 unit
2. CPU utilization between 60% and 80%, then add 2 units
3. CPU utilization greater that 80%, then add 4 units

##### Scheduled Actions

Anticipate a scaling based on known usage patterns. Example: increase the min capacity to 10  
at 5 pm on Fridays.

##### Predictive Scaling

Continuously forecast load and schedule scaling ahead

##### Cooldown Period

For each Auto Scaling Group, there's a Cooldown Period after each scaling activity. In this  
period, the ASG doesn't launch or terminate EC2 instances. This gives time to metrics to  
stabilize. The default value for the Cooldown Period is 300 seconds (5 minutes).

##### Standby State

Auto scalingdoes not perform health checks on instancesin the standby state. Standby state  
can beused for performing updates/changes/troubleshootingwithout health checks being  
performed or replacement instances being launched.
![[Pasted image 20230816214152.png]]
###### Auto Scaling Launch Configuration or Launch Templates (newer)

● Specify: AMI + Instance Type, EC2 User Data, EBS Volumes, Security Groups, SSH Key  
Pair  
● To update an ASG, you must provide a new launch configuration / launch template  
● Launch Templates do support a mix of On-Demand and Spot instances  
● defining a launch template instead of a launch configuration allows you to have multiple  
versions of a template.  
● With **launch templates only** , you can **provision capacityacross multiple instance types**  
using both On-Demand Instances and Spot Instances to achieve the desired scale,  
performance, and cost.

###### Auto Scaling Group

● Min Size / Max Size / Initial Capacity  
● May reference an ELB  
● Health Check Type