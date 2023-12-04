# Global Infrastructure && Reliability
****
- [X] Benefits of the AWS Global Infrastructure
- [X] Basic concept of Availability Zones
- [X] Benefits of Amazon CloudFront and Edge locations
- [X] Different methods for provisioning AWS services

****
### Points of consideration to choose an AWS Region
When it come to select a region, it have 4 points of consideration.
1. Compliance with data governance and legal 
    - some compnay requires all of its data reside within certain region, UK for example.
2. Proximity to the customers
    - Selecting a region that's close to customers
    - content can be send to customers faster
3. Availability services within a region
    - Certain services only available in certain region
4. Pricing
    - same services in different region may have different pricing

---
### Availability Zones

An Availability Zone (AZ) is a single data center or a group of data centers within a Region.

Best practice for customers is to run applications across at least tow Availability Zones in a Region. So that when an Availability Zone fail, the application is running on the other Availability Zone(s).

---
### Edge Location 
a site that Amazon CloudFront(AWS CDN) uses to store cached copies of your content closer to your customers for faster delivery.

[Content Delivery Network Youtube video](/https://www.youtube.com/watch?v=Bsq5cKkS33I)

---
### Methods of Provisioning AWS
Interact with all the AWS services through API calls

**Ways to interact with AWS services**

1. AWS Management Console
    - web-based interface for accessing and managing AWS services.
2. AWS Command Line Interface
    - automate the actions that your services and applications perform through scripts.
    - automate the actions that your services and applications perform through scripts.
3. AWS Software Development Kits
    - SDKs make it easier for you to use AWS services through an API designed for your programming language or platform.
    - SDKs enable you to use AWS services with your existing applications or create entirely new applications that will run on AWS.

**AWS Management tools to provision AWS services**

1. AWS Elastic Beanstalk
    - User provide code and configuration settings
    - Elastic Beanstalk deploys the resources to perfecm the following task:
        - Adjust capacity
        - Load Balancing
        - Automatic Scaling
        - Application health monitoring

2. AWS CloudFormation
    - User can treat the infrastructure aas code
    - User can build an environment by writing lines of code instead of using the console to provision the resources individually