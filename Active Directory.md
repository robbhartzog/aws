#### Simple AD

Simple AD is a standalone directory in the cloud, where you create and manage user identities  
and manage access to applications. Simple AD provides a subset of the features offered by  
AWS Managed Microsoft AD. However, note that Simple AD does not support features such as  
multi-factor authentication (MFA), trust relationships with other domains, Active Directory  
Administrative Center, PowerShell support, Active Directory recycle bin, group managed service  
accounts, and schema extensions for POSIX and Microsoft applications.

#### AD Connector

AD Connector is a **directory gateway** with which youcan redirect directory requests to your  
on-premises Microsoft Active Directory without caching any information in the cloud. AD  
Connector is your best choice when you want to use your existing on-premises directory with  
compatible AWS services.

#### AWS Managed Microsoft AD

AWS Directory Service lets you run Microsoft Active Directory (AD) as a managed service. AWS  
Directory Service for Microsoft Active Directory, also referred to as AWS Managed Microsoft AD,  
is powered by Windows Server 2012 R2. When you select and launch this directory type, it is  
created as a highly available pair of domain controllers connected to your virtual private cloud  
(VPC).

With AWS Managed Microsoft AD, you can run directory-aware workloads in the AWS Cloud,  
including Microsoft SharePoint and custom .NET and SQL Server-based applications. You can

also configure a trust relationship between AWS Managed Microsoft AD in the AWS Cloud and  
your existing on-premises Microsoft Active Directory, providing users and groups with access to  
resources in either domain, using single sign-on (SSO).

AWS Managed Microsoft AD is your best choice if you need actual Active Directory features to  
support AWS applications or Windows workloads, including Amazon Relational Database  
Service for Microsoft SQL Server. It's also best if you want a standalone AD in the AWS Cloud  
that supports Office 365 or **you need an LDAP directoryto support your Linux applications**.