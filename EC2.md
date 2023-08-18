When an EC2 instance is stopped & restarted (not rebooted) it gets a new Public IP address,  
but the _Private IP remains the same_.

You pay only for running instances, not when they are stopped (except for Reserved Instances)

You are limited to running On-Demand Instances per your vCPU-based On-Demand Instance  
limit, purchasing 20 Reserved Instances, and requesting Spot Instances per your dynamic Spot  
limit per region.

For all new accounts there is a soft limit of 20 EC2 instances per region.??

Xen and Nitro are the underlying hypervisors for EC2.

The two different types of virtualization available are Hardware Virtual Machine (HVM) &  
Paravirtual Machine (PVM).

When copying an AMI, which of the following types of information must be manually copied to  
the new instance? Launch permissions, S3 bucket permissions, and user-defined tags must be  
copied manually to an instance based on an AMI. User data is part of the AMI, itself, and does  
not need to be copied manually.

#### EC2 User Data

● It is possible to bootstrap our instances using an EC2 User Data script. Bootstrapping  
means launching commands when a machine starts.

● User Data script is **only run once at the instancefirst start**

● User Data script is used to automate boot tasks such as:

```
○ Installing updates, installing software, downloading common files from the internet
```

● User Data script runs as the root user

#### Connecting to EC2 instance

Connect to your EC2 instance using the following command:

ssh -i AWS_ID_KeyPair.pem ec2-user@54.173.22.

ssh -i id_key.pem ubuntu@54.173.22.

When you download the key (pem file) it has 0644 permission. You must change it to 0400.

#### EC2 meta-data

You can use the following command to get information about an instance. This command gets  
the top-level metadata items:curl [http://](http:) **169. 254. 169. 254** /latest/meta-data

Get Public IP:curl [http://169.254.169.254/latest/meta-data/public-ipv](http://169.254.169.254/latest/meta-data/public-ipv)

Get Instance Type:curl  
[http://169.254.169.254/latest/meta-data/instance-type](http://169.254.169.254/latest/meta-data/instance-type)

To enable **EC2 Hibernate** , the EC2 Instance Root Volumetype must be an EBS volume and  
must be encrypted to ensure the protection of sensitive content.

#### EC2 Instance Types

Compute Optimized EC2 instances are great for compute-intensive workloads requiring high  
performance processors, such as batch processing, media transcoding, high performance web  
servers, high performance computing, scientific modeling & machine learning, and dedicated  
gaming servers.

#### EC2 Pricing

```
On Demand Highest cost; Pay for usage; With Linux EC2 instances, you pay
per second of compute capacity. There is also a minimum of 60s
of use.
```

```
Reserved Instance (RI) Reserve for 1yr or 3yr; Sizable discount
```

```
Convertible RI can change the EC2 instance type
```

```
Scheduled RI launch within time window you reserve; for 1 yr only
```

```
Spot Instance Heavily discounted but can lose instance if your max price is
less than the current spot price
```

```
Spot Block request instances for 1 to 6 hours at a time to avoid being
interrupted while your job completes
```

```
Dedicated Host Physical server with EC2 instance capacity fully dedicated to
your use. Useful for software that have complicated licensing
model (BYOL - Bring Your Own License)
```

```
Dedicated Instance Instances running on hardware that’s dedicated to you. May
```

```
share hardware with other instances in same account
```

**Reserved instance** pricing is designed for workloadswith continuous and predictable usage  
and requires **1 or 3 year commitment**. It offers upto 75% discount over on-demand pricing.  
Unused Standard Reserved Instances can later be sold at the Reserved Instance Marketplace.  
You can reserve capacity to a specific AWS Region (regional Reserved Instance) or specific  
Availability Zone (zonal Reserved Instance) only.

You can change the tenancy of an instance from dedicated to host and from host to dedicated.

**Spot instances** allow you to use unused EC2 capacityat steep discounts of up to 90%.  
However, these instances can be interrupted any time with a 2 minute warning.

When you cancel an active spot request, it does not terminate the associated instance.

If a spot request is persistent, then it is opened again after your Spot Instance is interrupted.
![[Pasted image 20230816213921.png]]

**Spot Block** allows you to request spot instances forspecified duration **from 1 to 6 hours**.  
These instances are guaranteed to run without interruption for block duration requested. It offers  
a 30 to 50% discount over on-demand pricing.

With EC2 you are billed either by the second, for Linux or Windows instances (min 1 minute), or  
by the hour for all other instance types.

**On-Demand Capacity Reservations** enable you to reserve compute capacity for your Amazon  
EC2 instances in a specific Availability Zone for any duration. This gives you the ability to create  
and manage Capacity Reservations independently from the billing discounts offered by Savings  
Plans or Regional Reserved Instances.

By creating Capacity Reservations, you ensure that you always have access to EC2 capacity  
when you need it, for as long as you need it. You can create Capacity Reservations at any time,  
without entering a one-year or three-year term commitment, and the capacity is available  
immediately.

#### Spot Fleets

● Spot Fleets = set of Spot Instances + (optional) On-Demand Instances  
● It allows you to automatically request Spot Instances with the lowest price.  
● The Spot Fleet will try to meet the target capacity with price constraints - they maintain  
target capacity by launching replacement instances after Spot Instances in the fleet are  
terminated.

#### EC2 instance recovery

Terminated instances cannot be recovered. A recovered instance is identical to the original  
instance, including the instance ID, private IP addresses, Elastic IP addresses, and all instance  
metadata. If the impaired instance is in a placement group, the recovered instance runs in the  
placement group. If your instance has a public IPv4 address, it retains the public IPv4 address

after recovery. During instance recovery, the instance is migrated during an instance reboot, and  
any data that is in-memory is lost.

The recover action is supported only on instances that have EBS volumes configured on them;  
instance store volumes are not supported for automatic recovery by CloudWatch alarms.

#### AMI

**EC2 Image Builder** is an automated pipeline for thecreation, maintenance, validation, sharing,  
and deployment of Linux or Windows images for use on AWS and on-premises.