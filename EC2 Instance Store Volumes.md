● Used for better performance as compared to EBS volume  
● Instance Store Volumes are sometimes called Ephemeral Storage. You will **lose data when  
the EC2 instance is stopped**. If the underlying hostfails, you will lose your data.  
● Instance Store Volumes cannot be stopped.  
● Good use cases: buffer / cache / scratch data / temporary content  
● EBS backed instances can be stopped. You will not lose the data on this instance if it is  
stopped.  
● You can reboot both, you will not lose your data  
● By default, both ROOT volumes will be deleted on termination. However, with EBS volumes,  
you can tell AWS to keep root device volume  
● Termination protection is **turned off by default** , youmust turn it on.

● On an EBS-backed instance, the **default action is forthe root EBS volume to be deleted**  
when the instance is terminated.  
● EBS Root Volumes of your DEFAULT AMI’s cannot be encrypted. You can use a third party  
tool (such as bit locker etc) to encrypt the root volume, or this can be done when creating  
AMIs in the AWS console or using the API  
● Additional volumes can be encrypted.