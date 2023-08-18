## Identity Access Management (IAM)

● IAM consists of: Users, Groups, Roles, Policies

```
● Users: users created within an account
```

```
● Groups: users can be members of groups, but groupscannot be members of other
groups. Group is used for managing users and is notconsidered an identity. So, it
cannot be specified as a principal in resource level policies.
```

```
● Roles: temporary identities used by EC2 instances, Lambdas andexternal users
```

```
● Federation: Users with Active Directory identities or other corporate credentials have role
assigned in IAM
```

```
● Web Identity Federation: Users with web identities from Amazon.com or other Open ID
provider have role assigned using Security Token Service (STS)
```

● IAM is **universal (global)** and not region specific

● The “root account” is simply the account created when you first set up your AWS account. It  
has complete Admin access.

● New users have **NO permissions** when first created

● New users are assigned **Access Key ID** & **Secret AccessKeys** when first created. These  
are not the same as console password. They are used to access AWS via API and CLI. **You  
get to view these only once**. So, store them in a securelocation. If you lose them, you will  
have to regenerate them.

It isnot possible to put IP restrictionson rootuser logins.

Youcannot remove administrative permissionsfromthe root user of an AWS account.

**IAM Credentials report** lists all your account's usersand the status of their various credentials.  
**IAM Access Advisor** shows the service permissions grantedto a user and when those services  
were last accessed.

#### Managed Policies

Managed policy lives independently of the attached entity. If the attached entity is removed, the  
managed policy is not impacted.

Managed policies are reusable with automatic versioning.

With IAM policies, you can **only grant users withinyour own AWS account** permission to  
access your Amazon S3 resources.

#### IAM Permissions Boundary

AWS supports permissions boundaries for IAM entities (users or roles). A permissions boundary  
is an advanced feature for using a managed policy to set the maximum permissions that an  
identity-based policy can grant to an IAM entity. An entity's permissions boundary allows it to  
perform only the actions that are allowed by both its identity-based policies and its permissions  
boundaries. Here we have to use an IAM permission boundary. They can only be applied to  
roles or users, not IAM groups.

#### Cross Account Access

Cross account access is granted in two steps: resource owner account needs to trust the  
requester account and requester needs to explicitly delegate permissions to other IAM users in  
the requester's account. If permissions are not explicitly delegated, only the requester's root

account and administrative accounts can access resources in the other account. Account to  
account trust can be established using IAM Roles or by using resource level policies.

**Scenario** : Account B needs read access to a bucketowned by Account A. For this, create an  
IAM role in Account A with Account B as a trusted entity. Attach necessary read permission to  
this role.

#### Service control policies

Service control policies (SCPs) are one type of policy that you can use to manage your  
organization. SCPs offer central control over the maximum available permissions for all  
accounts in your organization, allowing you to ensure your accounts stay within your  
organization’s access control guidelines. **SCPs areavailable only in an organization that has  
all features enabled. SCPs aren't available if your organization has enabled only the  
consolidated billing features.** Attaching an SCP toan AWS Organizations entity (root, OU, or  
account) defines a guardrail for what actions the principals can perform.

SCPs affect all users and roles in attached accounts, including the root user.

SCPs **do not affect service-linked roles**.

### Tasks that require root user credentials

You can perform the tasks listed below **only when yousign in as the root user of an  
account**.

● **Change your account settings**. This includes the accountname, email address, root user  
password, and root user access keys. _Other accountsettings, such as contact information,  
payment currency preference, and Regions,_ **_do not_** _requireroot user credentials._  
● **Restore IAM user permissions**. If the only IAM administratoraccidentally revokes their  
own permissions, you can sign in as the root user to edit policies and restore those  
permissions.  
● **Activate IAM access to the Billing and Cost Management console**.

● **View certain tax invoices**. An IAM user with the aws-portal:ViewBillingpermission can view  
and download VAT invoices from AWS Europe, but not AWS Inc or Amazon Internet  
Services Pvt. Ltd (AISPL).  
● **Close your AWS account**.  
**● Change orCancel your AWS Support plan**  
● Register as a sellerin the Reserved Instance Marketplace.  
● Configure MFA deletefor your S3 bucket.  
**● Edit or delete an Amazon S3 bucket policy that includes an invalid VPC ID or VPC  
endpoint ID**

● Sign up for GovCloud