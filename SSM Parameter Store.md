SSM Parameters Store provides secure, hierarchical storage for configuration data  
management and secrets management. You can store data such as passwords, database  
strings, EC2 instance IDs, Amazon Machine Image (AMI) IDs, and license codes as parameter  
values. You can store values as plain text or encrypted data. You can reference Systems  
Manager parameters in your scripts, commands, SSM documents, and configuration and  
automation workflows by using the unique name that you specified when you created the  
parameter.

Each time you edit the value of a parameter, SSM Parameter Store creates a new version of the  
parameter and retains the previous versions. You can view the details, including the values, of  
all versions in a parameter's history.

**SSM Parameter Store can serve as a secrets store, but you must rotate the secrets  
yourself, it doesn't have an automatic capability for this.**

#### Secrets Manager

Secrets Manager helps you protect secrets needed to access your applications, services, and IT  
resources. The service enables you to easily rotate, manage, and retrieve database credentials,  
API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets  
with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in  
plain text. Secrets Manager **offers secret rotationwith built-in integration** for Amazon RDS,  
Amazon Redshift, and Amazon DocumentDB. You can configure Secrets Manager to  
automatically rotate the secret for you according to a schedule that you specify.