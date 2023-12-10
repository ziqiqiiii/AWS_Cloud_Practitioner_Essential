# Prcing and Support

- [X] Describe AWS pricing and support models.
- [X] Describe the AWS Free Tier.
- [X] Describe key benefits of AWS Organizations and consolidated billing.
- [X] Explain the benefits of AWS Budgets.
- [X] Explain the benefits of AWS Cost Explorer.
- [X] Explain the primary benefits of the AWS Pricing Calculator.
- [X] Distinguish between the various AWS Support Plans.
- [X] Describe the benefits of AWS Marketplace.

---
### AWS Free Tier 
The AWS Free Tier(opens in a new tab) enables you to begin using certain services without having to worry about incurring costs for the specified period. 

Three types of offers are available: 

- Always Free
- 12 Months Free
- Trials

---
### AWS Pricing Concepts
AWS have 3 pricing catogories:
1. Pay for what you use
    For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing.
2. Pay less when you reserve
    Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.
    For example, AMW EC2.
3. Pay less with volume-based discounts when you use more
    Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage.
    For example, the more Amazon S3 storage space you use, the less you pay for it per GB.

#### AWS Pricing Calculator
The AWS Pricing Calculator(opens in a new tab) lets you explore AWS services and create an estimate for the cost of your use cases on AWS. You can organize your AWS estimates by groups that you define. A group can reflect how your company is organized, such as providing estimates by cost center.

#### AWS Pricing Examples
##### AWS Lambda
- For AWS Lambda, you are charged based on the number of requests for your functions and the time that it takes for them to run.
- AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month.

##### Amazon EC2
- With Amazon EC2, you pay for only the compute time that you use while your instances are running.

##### Amazon S3
For Amazon S3 pricing, consider the following cost components:

- **Storage** 
    You pay for only the storage that you use. You are charged the rate to store objects in your Amazon S3 buckets based on your objects’ sizes, storage classes, and how long you have stored each object during the month.
- **Requests and data retrievals** 
    You pay for requests made to your Amazon S3 objects and buckets. For example, suppose that you are storing photo files in Amazon S3 buckets and hosting them on a website. Every time a visitor requests the website that includes these photo files, this counts towards requests you must pay for.
- **Data transfer**
    There is no cost to transfer data between different Amazon S3 buckets or from Amazon S3 to other services within the same AWS Region. However, you pay for data that you transfer into and out of Amazon S3, with a few exceptions. There is no cost for data transferred into Amazon S3 from the internet or out to Amazon CloudFront. There is also no cost for data transferred out to an Amazon EC2 instance in the same AWS Region as the Amazon S3 bucket.
- **Management and replication** 
    You pay for the storage management features that you have enabled on your account’s Amazon S3 buckets. These features include Amazon S3 inventory, analytics, and object tagging.

    ---