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
| Similarities                                                              |
|:-------------------------------------------------------------------------:|
| - Both use the AWS global network and its edge locations around the world |
| - Both services integrate with AWS Shield for DDoS protection             |

| Differences                                                                            |
| CloudFront                                    | Global Accelerator                     |
|----------------------------------------------|-----------------------------------------|
| - CDN                                        | 
| - Improves performance for cacheable content |
| - Content is served at the Edge Location     |

