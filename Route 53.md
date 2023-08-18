● Route 53 is a scalable and highly available Domain Name System (DNS) service

● features include domain registration, DNS, traffic flow, health checking, and failover.  
● ELBs do no have a pre-defined IPv4 addresses; you resolve them using a DNS name  
● Understand the difference between a Alias Record and a CNAME  
○ **A** Records are the most basic type of DNS record andare used to point a domain or  
subdomain to an IP address.  
○ CNAME records are another commonly used type of DNS entry and are used to point a  
domain or subdomain to another hostname (not IP address).  
○ You can create an alias record at the top node of a DNS namespace, also known as the  
zone apex, however, **you cannot create a CNAME recordfor the top node of the  
DNS namespace**. So, if you register the DNS name covid19survey.com,the zone apex  
is covid19survey.com. You can't create a CNAME record for covid19survey.com, but you  
can create an alias record for covid19survey.com that routes traffic to  
[http://www.covid19survey.com.](http://www.covid19survey.com./)  
○ An alias record can only redirect queries to selected AWS resources such as S3  
buckets, CloudFront distributions, and another record in the same Route 53 hosted  
zone; however a CNAME record can redirect DNS queries to any DNS record. So, you  
can create a CNAME record that redirects queries from app.covid19survey.com to  
app.covid19survey.net.  
○ For Alias Records, TTL value of the resource that is pointed to by Alias Records are  
used. Route 53 does not allow you to set or override the Alias Record TTLs  
● Zone Apex record or naked domain name  
**● Given a choice,always choose Alias Record over a CNAME** (Route 53 doesn't charge for  
alias queries to AWS resources but Route 53 does charge for CNAME queries.)  
● You can buy a domain name from AWS. It can take up to 3 days to register the domain  
depending on circumstances.

In AWS, the most common records are:

● [http://www.google.com](http://www.google.com/) => 12.34.56.78 == **A record** (IPv4)  
● [http://www.google.com](http://www.google.com/) => 2001:0db8:85a3:0000:0000:8a2e:0370:7334 == **AAAA** IPv6  
● search.google.com => [http://www.google.com](http://www.google.com/) == **CNAME** : hostnameto hostname  
● example.com => AWS resource == **Alias** (ex: ELB, CloudFront,S3, RDS, etc...)

##### Simple Routing Policy

● has one record with multiple IP addresses  
● If you specify multiple IP addresses, Route 53 returns all values to the user in a random  
order.  
● There is no health check available

##### Weighted Routing Policy

● Allows your traffic to be split based on different weights assigned. For e.g. you can set 10%  
of your traffic to got to US-EAST-1 and 90% to go to EU-WEST-1

##### Latency based routing

● Checks network latency and sends traffic to server with lowest latency

##### Failover Routing

● Used when you want to create active-passive setup

##### Geolocation Routing Policy

● Route traffic based on geolocation  
● restrict the distribution of content to only certain locations

##### Geoproximity Routing

● Lets Amazon Route 53 route traffic to your resources based on geographic locations of your  
users and your resources.You can optionally choose to route more traffic or less to a given  
resource by specifying a value, known as bias. A bias expands or shrinks the size of the  
geographic region from which traffic is routed to a resource. This policy MUST use Route 53  
traffic flow.

##### Multivalue Answer Policy

● This is similar to Simple Routing policy but you can have health checks on individual values  
and traffic will be automatically rerouted if the health check fails.

##### Health Check

● You can set health check on individual record sets  
● If a record set fails health check it will be removed from Route 53 until it passes the health  
check  
● You can set SNS notifications to alert you if a health check fails

Route 53 has a security feature thatprevents internal DNS from being read by external sources.  
The work around is to create a EC2 hosted DNS instance that does zone transfers from the  
internal DNS, and allows itself to be queried by external servers.