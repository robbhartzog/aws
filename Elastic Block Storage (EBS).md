● Elastic Block Storage is a virtual/network drive.  
● Provides persistent block storage volumes for use with EC2 instances.  
● Each EBS volume is _automatically replicated withinits AZ_ to protect you from component  
failure, offering high availability and durability.  
● EBS is locked to AZ. To move to a different AZ/region, take a snapshot and restore it at the  
destination.  
● You arechargedfor theamount of data provisioned(not consumed) per month. This means  
you can have empty space within a volume and you still pay for it. With provisioned IOPS  
volumes you are also charged for theamount you provisionin IOPS  
**● EBS does not support SMB protocol.**  
● Default behavior is **EBS will stop** I/O to the volumeif it detects **potential data  
inconsistencies** in the volume. This is to preventdata corruption. Volume status check  
would report this condition as Impaired.

##### General Purpose SSD

```
gp3 Baseline of 3,000 IOPS and throughput of 125 MiB/s
Can increase IOPS up to 16,000 and throughput up to 1000 MiB/s independently
```

```
gp2 Small gp2 volumes can burst IOPS to 3,
Size of the volume and IOPS are linked, max IOPS is 16,
3 IOPS per GB, means at 5,334 GB we are at the max IOPS
```

##### Provisioned IOPS SSD

● Critical business apps with sustained IOPS or require more than 16000 IOPS  
● Max PIOPS: 64,000 for Nitro EC2 instances & 32,000 for other  
● io2 have more durability and more IOPS per GiB (at the same price as io1)  
● EBS io2 Block Express - next generation EBS supporting up to 256000 IOPS  
● Supports EBS Multi-attach