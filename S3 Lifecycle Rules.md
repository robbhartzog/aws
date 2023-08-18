You can create a S3 lifecycle policy that expires incomplete multipart uploads, allowing you to  
save on costs by limiting the time non-completed multipart uploads are stored.

Before you transition objects from the S3 Standard or S3 Standard-IA storage classes to S3  
Standard-IA or S3 One Zone-IA, you must store them for at least 30 days in the S3 Standard  
storage class.

You can transition from S3 to S3 Glacier or S3 Glacier Deep Archive earlier.
![[Pasted image 20230816214229.png]]