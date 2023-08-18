● Federation allows users to authenticate with a Web Identity Provider (Amazon, Google,  
Facebook)

● The user authenticates first with the Web Identity Provider and receives an authentication  
token, which is exchanged for temporary AWS credentials allowing them to assume an IAM  
role.  
● Cognito is an Identity Broker which handles interaction between your application and the  
Web ID provider  
● User pool is user based and handles user registration, authentication and account recovery  
● Identity pools authorize access to your AWS resources