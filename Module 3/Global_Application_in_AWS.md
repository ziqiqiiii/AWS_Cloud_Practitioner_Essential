## Global Applications in AWS

---
### Global DNS
**Route 53**
- Great to route users to the closest deployment with least latency
- Great for disaster recovery strategies

**What's Amazon Route 53**
- Route53 is a Managed DNS (Domain Name System)
- [What is DNS (Domain Name System) ?](https://www.youtube.com/watch?v=nyH0nYhMW9M)
- DNS is a collection of rules and records which helps clients understand how to reach a server through URLs

**Route53 Routing Policies**

1. Simple Routing Policy
2. Weighted Routing Policy
3. Latency Routing Policy
4. Failover Routing Policy (Disaster Recovery)

---
### Global Content Delivery Network (CDN)
**CloudFront**
- Replicate part of the application to AWS Edge Locations to decrease latency
- Cache common requests to improved user experience and decrease latency
- 216 Point of Presence globally (Edge Locations)


---

### S3 Transfer Acceleration
- Accelerate global uploads and downloads into Amazon S3
- Increase transfer speed by transfering file to an AWS Edge Location which will forward the data to the S3 bucket in the target region

--- 

### AWS Global Accelerator
- Improv global application availability and performance using the AWS global network
- Leverage the AWS internal network to optimize the route to your application

---

#### Differences and Similarities between AWS Global Accelerator vs CloudFront
|Similarities                                                               |
|---------------------------------------------------------------------------|
| - Both use the AWS global network and its edge locations around the world |
| - Both services integrate with AWS Shield for DDoS protection             |

Differences  

| CloudFront                                   | Global Accelerator                     |
|----------------------------------------------|-----------------------------------------|
| - CDN                                        | - No caching, proxying packets at the edge to applications running in one or more AWS Regions. |
| - Improves performance for cacheable content | - Improves Performance for a wide range of applications over TCP OR UDP |
| - Content is served at the Edge Location     | - Good for HTTP use cases that require static IP addresses |
|                                              | - Good for HTTP use cases that required deterministi, fast regional failover |

---

### AWS Outposts

Some clients use ***Hybrid Cloud***: using both on-premises infrastructure alongside a cloud infrastructure.
AWS Outposts are "server racks" that offers the same AWS infrastructure, services, APIs, and tools for clients to build their own applications on-premises just as in the cloud.
AWS will setup and manage "Outposts Racks" within clients' on-premises infrastructure and clients can start leveraging AWS services on-premises

**Benefits**
- Low-latency access to on-premises systems
- Local data processing
- Data residency 
- Easier migration from on-premises to the cloud
- Fully managed service
