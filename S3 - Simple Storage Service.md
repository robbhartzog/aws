The key fundamentals of S3 are:

● Key (this is simply the name of the object). S3 bucket names must be globally unique.

● Value (this is simply the data and is made up of a sequence of bytes)  
● Version ID (important for versioning)  
● Metadata (data about data you are storing)  
● Subresources; Access Control Lists  
● There are two ways of securing S3, using either Access Control Lists (Permissions) or by  
using bucket policies.  
● By **default** , customers can provision up to **100 bucketsper AWS account**. However, you  
can increase your Amazon S3 bucket limit by visiting AWS Service Limits.  
● By default, an S3 object is owned by the AWS account that uploaded it. This is true even  
when the bucket is owned by another account.  
● Amazon S3 delivers **strong read-after-write consistencyautomatically** , without changes  
to performance or availability, without sacrificing regional isolation for applications, and at no  
additional cost.  
● After a successful write of a new object or an overwrite of an existing object, any subsequent  
read request immediately receives the latest version of the object. S3 also provides **strong  
consistency for list operations** , so after a write,you can immediately perform a listing of  
the objects in a bucket with any changes reflected.  
● **S3 notification feature** enables you to receive notificationswhen certain events happen in  
your bucket. Add a notification configuration identifying the events you want Amazon S3 to  
publish, and the destinations where you want Amazon S3 to send the event notifications  
(SQS (standard, not FIFO), Lambda and SNS).  
● Amazon S3 server access logs provide detailed records for the requests that are made to  
an S3 bucket.  
● Amazon S3 now provides increased performance to support at least 3,500 requests per  
second to add data and 5,500 requests per second to retrieve data, which can save  
significant processing time for no additional charge. Each S3 prefix can support these  
request rates, making it simple to increase performance significantly.