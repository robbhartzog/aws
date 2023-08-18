#### QLDB

Amazon QLDB is a fully managed ledger database that provides a transparent, immutable, and  
cryptographically verifiable transaction log owned by a central trusted authority. Amazon QLDB  
is not a blockchain or distributed ledger technology.

Amazon QLDB tracks each and every application data change and maintains a complete and  
verifiable history of changes over time.

#### Managed Blockchain

Amazon Managed Blockchain is a fully managed service that makes it easy to create and  
manage scalable blockchain networks using the popular open source frameworks Hyperledger  
Fabric and Ethereum. It allows multiple parties to execute transactions without the need of a  
trusted, central authority.

#### Neptune

Amazon Neptune is a fast, reliable, fully-managed graph database service that makes it easy to  
build and run applications that work with highly connected datasets. It can be used for  
knowledge graphs, fraud detection, recommendations engines, social networking, etc.

#### QuickSight

Amazon QuickSight is a fast, cloud-powered business intelligence (BI) service that makes it  
easy for you to deliver insights to everyone in your organization. You can create and publish  
interactive dashboards.

#### DocumentDB

Amazon DocumentDB (with MongoDB compatibility) is a fast, calable, highly available, and fully  
managed document database service that supports MongoDB workloads.

#### Lightsail

Amazon Lightsail is designed to be the easiest way to launch and manage a virtual private  
server with AWS. Lightsail plans include everything you need to jumpstart your project – a  
virtual machine, SSD- based storage, data transfer, DNS management, and a static IP address

- for a low, predictable price. It can be used to create a simple web application, a website or a  
    dev/test environment.

#### Batch

AWS Batch can be used to plan, schedule, and execute your batch computing workloads on  
Amazon EC2 Instances. AWS Batch enables developers, scientists, and engineers to easily and  
efficiently run hundreds of thousands of batch computing jobs on AWS. AWS Batch dynamically  
provisions the optimal quantity and type of compute resources (e.g., CPU or memory-optimized  
instances) based on the volume and specific resource requirements of the batch jobs submitted.

#### CodeArtifact

● secure, scalable, and cost-effective artifact management for software development

#### CodeStar

● Unified UI to easily manage software development activities in one place  
● “Quick way” to get started to correctly set-up CodeCommit, CodePipeline, CodeBuild,  
CodeDeploy, Elastic Beanstalk, EC2, etc...

#### AWS Cloud9

● Browser-based, cloud IDE for writing, running and debugging code  
● Allows for code collaboration in real-time (pair programming)

#### AWS Artifact (different from CodeArtifact)

AWS Artifact is your go-to, central resource for compliance-related information that matters to  
you. It provides on-demand access to AWS security and compliance reports and select online  
agreements.

You can use AWS Artifact Reports to download AWS security and compliance documents, such  
as AWS ISO certifications, Payment Card Industry (PCI), and System and Organization Control  
(SOC) reports.

#### GuardDuty

Amazon GuardDuty is a threat detection service that continuously monitors for malicious activity  
and unauthorized behavior to protect your AWS accounts, workloads, and data stored in  
Amazon S3.

GuardDuty analyzes tens of billions of events across multiple AWS data sources, such as AWS  
CloudTrail events, Amazon VPC Flow Logs, and DNS logs.

#### CloudEndure

AWS provides CloudEndure Disaster Recovery for creating a full replica of your on-premises  
servers, including the root volume and operating system, on AWS. CloudEndure Disaster  
Recovery continuously replicates your machines into a low-cost staging area in your target AWS  
account and preferred Region.

#### Inspector

Inspector is an automated **security assessment servicethat helps improve the security and  
compliance of applications** deployed on AWS. Inspector automatically **assesses  
applications for vulnerabilities or deviations from best practices**.

#### Web Application Firewall (WAF)

AWS WAF is a web application firewall that protects against common exploits that could  
compromise application availability, compromise security or consume excessive resources.

AWS WAF is tightly integrated with Amazon CloudFront, the Application Load Balancer (ALB),  
Amazon API Gateway, and AWS AppSync

AWS WAF **can be used to protect on-premises resourcesif they are deployed behind an  
Application Load Balancer (ALB)**. In this scenariothe on-premises website servers are added  
to a target group by IP address. The ALB has a WAF WebACL attached to it and distributes  
connections to the on-premises website.

WAF is a **global service**. When you configure it inthe AWS management console you will see  
that the scope is set to “Global”.

#### AWS Firewall Manager

Using AWS Firewall Manager, you can centrally configure the following across accounts and  
resources in your organization:

● AWS WAF rules  
● AWS Shield Advanced protection  
● Amazon Virtual Private Cloud (VPC) security groups  
● AWS Network Firewalls, and  
● Amazon Route 53 Resolver DNS Firewall rules

**It does not support Network ACLs as of today.**

#### TCO Calculator

TCO calculators allow you to estimate the cost savings when using AWS, compared to  
on-premises, and provide a detailed set of reports that can be used in executive presentations.  
The calculators also give you the option to modify assumptions that best meet your business  
needs.

#### Managed Services

AWS Managed Services manages the daily operations of your AWS infrastructure in alignment  
with ITIL processes. AWS Managed Services **providesa baseline integration with IT Service  
Management (ITSM) tools** such as the ServiceNow platform.

AWS Managed Services provides ongoing management of your AWS infrastructure so you can  
focus on your applications. By implementing best practices to maintain your infrastructure, AWS  
Managed Services helps to reduce your operational overhead and risk.

AWS Managed Services currently supports the 20+ services most critical for Enterprises, and  
will continue to expand our list of integrated AWS services.

AWS Managed Services is designed to meet the needs of Enterprises that require stringent  
SLAs, adherence to corporate compliance, and integration with their systems and **ITIL®-based  
processes**.

#### X-Ray

● Visual analysis of our applications  
● trace requests made through your distributed applications  
● Understand dependencies in a microservice architecture  
● Pinpoint service issues  
● Troubleshooting performance (bottlenecks)  
● Find errors and exceptions

#### CodeGuru

● An ML-powered service for automated code reviews and application performance  
recommendations  
● Provides two functionalities  
○ CodeGuru Reviewer: automated code reviews for static code analysis (development)  
○ CodeGuru Profiler: visibility/recommendations about application performance during  
runtime (production)

#### Service Health Dashboard

● Shows all health of regions, all services & historical information  
● Website: https://status.aws.amazon.com/

#### Personal Health Dashboard

● AWS Personal Health Dashboard provides alerts and remediation guidance when AWS is  
experiencing events that may impact you.  
● While the Service Health Dashboard displays the general status of AWS services, Personal  
Health Dashboard gives you a **personalized view intothe performance and availability  
of the AWS services underlying your AWS resources**.  
● The dashboard displays **relevant and timely information** to help you manage events in  
progress and provides **proactive notification** to helpyou plan for **scheduled activities**.

#### AWS Well-Architected Tool

The AWS Well-Architected Tool helps you review the state of your workloads and compares  
them to the latest AWS architectural best practices. It is based on the 5 pillars of the  
Well-Architected Framework (Operational Excellence, Security, Reliability, Performance  
Efficiency, and Cost Optimization). AWS Trusted Advisor is an online tool that provides you real  
time guidance to help you provision your resources following AWS best practices (Cost  
Optimization, Performance, Security, Fault Tolerance, and Service Limits).

#### AWS Systems Manager

AWS Systems Manager allows you to **centralize operationaldata from multiple AWS  
services** and automate tasks across your AWS resources.You can create logical groups of  
resources such as applications, different layers of an application stack, or production versus  
development environments.

#### AWS Shield

AWS Shield is a managed Distributed Denial of Service ( **DDoS** ) protection service

#### Golden Image

Some resource types can be launched from a golden image. **A golden image is a snapshot** of  
a particular state for that resource. Examples are EC2 instances, RDS instances and EBS  
volumes.