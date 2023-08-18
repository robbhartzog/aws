AWS KMS provides an audit trail so you can see who used your key to access which object and  
when, as well as view failed attempts to access data from users without permission to decrypt  
the data.

To delete a CMK in AWS KMS you schedule key deletion. You can set the waiting period from a  
minimum of 7 days up to a maximum of 30 days. The default waiting period is 30 days. During  
the waiting period, the CMK status and key state is Pending deletion. To recover the CMK, you  
can cancel key deletion before the waiting period ends. After the waiting period ends you cannot  
cancel key deletion, and AWS KMS deletes the CMK.

#### CloudHSM

AWS CloudHSM is a cloud-based **hardware security module** (HSM) that enables you to easily  
generate and use your own encryption keys on the AWS Cloud.