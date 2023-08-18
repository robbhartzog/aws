Amazon Cloudwatch is a monitoring service to monitor your AWS resources, as well as the  
applications that you run on AWS.
![[Pasted image 20230816214817.png]]
You can use Amazon CloudWatch to collect and track metrics, monitor log files, set alarms, and  
automatically react to changes in your AWS resources. You can also use Amazon CloudWatch  
to gain system-wide visibility into resource utilization, application performance, and operational  
health.

You would like to monitor two different metrics in an AWS Service and take automated action  
based on the metric value. Alarm is associated with one metric. So, we need one alarm per  
metric.

When you recover an EC2 instance using CloudWatch Alarm, the instance is moved to a  
different physical host. Instance has the same metadata including public and private IP  
addresses.

#### CloudWatch Events (EventBridge)

**CloudWatch Events** delivers a near real-time streamof system events that describe changes  
in Amazon Web Services (AWS) resources. Using simple rules that you can quickly set up, you  
can match events and route them to one or more target functions or streams. CloudWatch  
Events becomes aware of operational changes as they occur. CloudWatch Events responds to  
these operational changes and takes corrective action as necessary, by sending messages to  
respond to the environment, activating functions, making changes, and capturing state  
information.

You can also use CloudWatch Events to schedule automated actions that self-trigger at certain  
times using cron or rate expressions. For more information, seeSchedule Expressions for  
Rules.

#### CloudWatch Metrics

● CloudWatch can monitor:  
○ CPU  
○ Network  
○ Queue Size  
○ CloudWatchcannot track memory utilization and hencememory utilization cannot be  
used to auto-scale.  
● Standard CloudWatch monitoring for EC2 instances is a 5 minute interval. Detail monitoring  
is 1 minute interval (not included in free tier).

Understand the difference between default and custom metrics.

#### CloudWatch Logs

● CloudWatch Logs can collect log from:  
○ Elastic Beanstalk: collection of logs from application  
○ ECS: collection from containers  
○ AWS Lambda: collection from function logs  
○ CloudTrail based on filter  
○ CloudWatch log agents: on EC2 machines or on-premises servers  
○ Route53: Log DNS queries  
● Enables real-time monitoring of logs  
● Adjustable CloudWatch Logs retention

#### CloudWatch Alarms

Using Amazon CloudWatch alarm actions, you can create alarms that automatically stop,  
terminate, reboot, or recover your EC2 instances. You can use the stop or terminate actions to  
help you save money when you no longer need an instance to be running. **You can use the  
reboot and recover actions to automatically reboot those instances or recover them onto  
new hardware if a system impairment occurs.**

You can create an Amazon CloudWatch alarm that monitors an Amazon EC2 instance and  
automatically reboots the instance. The reboot alarm action is recommended for Instance  
Health Check failures (as opposed to the recover alarm action, which is suited for System  
Health Check failures).