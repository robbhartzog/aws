EBS snapshots are accessible from within a region. You can copy snapshots from one region to  
another.

**Encrypt Root Device Volume**

● Snapshots exist on S3. Think of snapshots as a photograph of the disk. They are point in  
time copies of volumes  
● Snapshots can be shared only if they are unencrypted. These can be shared with other  
AWS accounts or made public.  
● Snapshots of encrypted volumes are encrypted automatically. Volumes restored from  
encrypted snapshots are encrypted automatically.

● You cannot create an unencrypted volume from an encrypted snapshot or encrypt an  
existing volume.  
● Snapshots are incremental - this means that only the blocks that have changed since your  
last snapshot are moved to S  
● To create a snapshot for Amazon EBS volumes that serve as root devices, you should stop  
the instance before taking the snapshot (recommended). However, you can take a snap  
while the instance is running  
● You can create AMIs from both Volumes and Snapshots  
● You can change EBS volume sizes on the fly, including changing the size and storage type  
● Volumes will always be in the same AZ as the EC2 instance.

To move an EC2 volume from one AZ to another, take a snapshot of it, create an AMI from the  
snapshot and then use the AMI to launch the EC2 instance in a new AZ.

To move an EC2 volume from one region to another, take a snapshot of it, create an AMI from  
the snapshot and then copy the AMI from one region to the other. Then use the copied AMI to  
launch the new EC2 instance in the new region.

Each EBS snapshot is given a unique identifier, and customers can create volumes based  
on any of their existing snapshots.

If you have an unencrypted root device volume, to encrypt it follow these steps:

1. Make a snapshot
2. Copy the snapshot and specify encrypt while copying
3. Create an AMI from the copy
4. Launch EC2 instance with this AMI

For a consistent snapshot of an EBS Volume, you need to ensure the application flushes any  
cached data to disk and no other write I/O is performed by the file system on that volume. Once  
that is taken care of, you can issue a snapshot command. The snapshot command needs only a  
couple of seconds to capture a point-in-time. You can start using the volume after this. The  
actual data backup happens in the background, and you don’t have to wait for the data copy to

complete. This approach gives you a predictable downtime irrespective of the size of the EBS  
Volume.

There are a couple of ways in which you change the encryption keys associated with an EBS  
volume: Change the key during the snapshot copy process. Another option is: from an EC  
instance, mount a new EBS volume with the desired key and copy data from old volume to new  
volume.

You can use Amazon Data Lifecycle Manager (Amazon DLM) to automate the creation,  
retention, and deletion of snapshots taken to back up your Amazon EBS volumes. Combined  
with the monitoring features of Amazon CloudWatch Events and AWS CloudTrail, Amazon DLM  
provides a complete backup solution for EBS volumes at no additional cost.

If the instance is already running, you can set _DeleteOnTermination_ to False using the  
command line (cannot be done through console).