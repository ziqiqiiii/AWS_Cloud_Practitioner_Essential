## Global Applications in AWS
Global application is an application deployed in multiple geograhies
Why make global applications ?
- Decrease latency
- Disaster Recovery (DR)
	- if an AWS Region goes down(earthquake, storms, power shutdown, politics)
	- Users can fail-over to another region and have their application still working
	- A DR plan is important to increase the availability of clients' applications
- Attack protection
	- Distributed global infrastructure is harder to attack

---
### Global DNS
**Route 53**
- Great to route users to the closest deployment with least latency
- Great for disaster recovery strategies
- Features available for Route 53:
	- Domain Registration
	- DNS
	- Health Checks
	- Routing Policy

**What's Amazon Route 53**
- Route53 is a Managed DNS (Domain Name System)
- [What is DNS (Domain Name System) ?](https://www.youtube.com/watch?v=nyH0nYhMW9M)
- DNS is a collection of rules and records which helps clients understand how to reach a server through URLs

**Route53 Routing Policies**

1. Simple Routing Policy
2. Weighted Routing Policy
	Route Traffic to multiple resources in proportions to users' specification
3. Latency Routing Policy
4. Failover Routing Policy (Disaster Recovery)

---
### Global Content Delivery Network (CDN)
**CloudFront**
- Replicate part of the application to AWS Edge Locations to decrease latency
- Cache common requests to improved user experience and decrease latency
- 216 Point of Presence globally (Edge Locations)
- CloudFront integrate WAF && Shield to protect against web attacks

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

---

### AWS Wavelength
AWS Wavelength combines the high bandwidth and ultralow latency of 5G networks with AWS compute and storage services so that developers can innovate and build a new class of applications.

Wavelength Zones are AWS infrastructure deployments that embed AWS compute and storage services within communication service providers' (CSP) 5G networks.
So, application traffic from 5G devices reach application server running in Wavelength Zones without leaving the telecommunications network.
This avoid latency which allows customers to take full advantage of the ultra-low-latency and bandwidth benefits offers by modern 5G networks.

**Use Cases**
- Build media and entertainment applications
	- High-resolution live video streaming
	- High-fidelity audio
	- Augmented / Virtual Reality (AR/VR) applications
- Accelerate ML inference at the edge
	- Run AI && ML driven video and images analytics at the edge 
	- e.g. medical diagnostic, retail, smart factory settings, sport analysis.
- Develop connected vehicle applications
	- Advanced driver assistance
	- autonomous driving
	- smart city applications

---

### AWS Local Zones
Places AWS compute storage, database, and other selected AWS services ***closer to end user to lun latency-sensitive applications***
- Extend your VPC (Virtual Private Cloud) to more locations
	- Extension of an AWS Region
- Examples:
	- AWS Region: Virginia
	- AWS Local Zone: Boston, Chicago, Dallas, Houston, Miami

---
### Differences in AWS Wavelenght Zones and AWS Local Zones

- You can use Local Zones (are an extension of an AWS Region) to place resources in multiple locations closer to your end users.

- You can use Wavelength Zones to build applications that deliver ultra-low latencies to 5G devices and end users. Wavelength deploys standard AWS compute and storage services to the edge of telecommunication carriers' 5G networks.