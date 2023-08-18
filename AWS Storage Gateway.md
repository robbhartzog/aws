Storage Gateway connects an on-premises software appliance with cloud-based storage.  
Storage Gateway provides integration with data security features between your on-premises IT  
environment and AWS storage infrastructure such as Amazon S3.

The Storage Gateway service is primarily used for attaching infrastructure located in a Data  
center or office to the AWS Storage infrastructure.

##### File Gateway

File gateway provides a virtual on-premises file server, which enables you to store and retrieve  
files as objects in Amazon S3. The File Gateway enables you to store and retrieve objects in  
Amazon S3 using file protocols such as Network File System (NFS) and Server Message Block  
(SMB).

##### Volume Gateway

Volume Gateway presents cloud-based **iSCSIblockstoragevolumes** to your on-premises  
applications. **It does not support NFS.**

**Stored Volumes** - Entire dataset is **stored on site** and is asynchronously backed up to S3

**Cached Volumes** - Entire dataset is **stored on S3** andthe most frequently accessed data is  
cached on site

##### Tape Gateway (Gateway Virtual Tape Library)

Tape Gateway (formerly known as Gateway Virtual Tape Library) is used for backup and uses  
popular backup applications like NetBackup, BackupExec, Veeam etc. Does not support NFS.

![[Pasted image 20230816214327.png]]![[Pasted image 20230816214339.png]]