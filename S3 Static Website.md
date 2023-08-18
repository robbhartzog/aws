Here are the prerequisites for routing traffic to a website that is hosted in an Amazon S3 Bucket:

● An S3 bucket that is configured to host a static website. The **bucket must have the same  
name as your domain or subdomain**. For example, ifyou want to use the subdomain  
portal.tutorialsdojo.com, the name of the bucket must be portal.tutorialsdojo.com.  
● A registered domain name. You can use Route 53 as your domain registrar, or you can use  
a different registrar.  
● Route 53 as the DNS service for the domain. If you register your domain name by using  
Route 53, we automatically configure Route 53 as the DNS service for the domain.  
● When you configure your bucket as a static website, the website is available at the AWS  
Region-specific website endpoint of the bucket.Depending on your Region, your Amazon S3  
website endpoints follow one of these two formats. These URLs return the default index  
document that you configure for the website.  
○ s3-website dash (-) Region ‐ [http://bucket-name.s3-website.Region.amazonaws.com](http://bucket-name.s3-website.region.amazonaws.com/)  
○ s3-website dot (.) Region ‐ [http://bucket-name.s3-website-Region.amazonaws.com](http://bucket-name.s3-website-region.amazonaws.com/)
![[Pasted image 20230816214245.png]]
#### S3 Static Website CORS

#### S3 Signed URLs

S3 Pre-Signed URLs are temporary URLs that you generate to grant time-limited access to  
some actions in your S3 bucket.

#### S3 Select

Retrieve less data using SQL by performing server side filtering

#### S3 Byte Range Fetch

● Parallelize GETs by requesting specific byte ranges (speed up downloads)  
● Better resilience in case of failures  
● Can be used to retrieve only partial data (for example the head of a file)

#### CloudFront (AWS content delivery network)

**Edge Location** - this is the location where contentwill be cached. This is different from an AWS  
Region/AZ

**Origin** - this is the origin of all the files thatthe CDN will distribute. This can be either a S3  
bucket, EC2 instance, Elastic Load Balancer or Route 53

**Distribution** - This is the name given to CDN whichconsists of Edge Locations

**Web Distribution** - typically used for websites

● Edge locations are not just READ only - you can write to them too (i.e. put an object on to  
them)  
● Objects are cached for the life of the TTL (Time To Live)  
● You can clear cached objects, but you will be charged

**CloudFront Signed URLs** are commonly used to distributepaid content through dynamically  
generated signed URLs.

Use **Signed Cookies** to provide access to hundreds ofprivate files served by your CloudFront  
distribution.

##### CloudFront Geo Restriction

##### Origin Access Identity (OAI)

You can use an OAI to restrict access to content in Amazon S3 but not on EC2 or ELB.

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data,  
videos, applications, and APIs to customers globally with low latency, high transfer speeds.  
Amazon CloudFront can be used in front of an Application Load Balancer.

If you have objects that are smaller than 1GB or if the data set is less than 1GB in size, you  
should consider using Amazon CloudFront. For larger sizes, S3 Transfer Acceleration is a better  
option.

```
{
    "Version":"2012-10-17",
    "Statement":[
      {
        "Sid":"PublicRead",
        "Effect":"Allow",
        "Principal": "*",
        "Action":["s3:GetObject"],
        "Resource":["arn:aws:s3:::examplebucket/*"]
      }
    ]
}
```