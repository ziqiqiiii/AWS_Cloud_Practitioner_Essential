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
### Billing Dashboard
Use the AWS Billing & Cost Management dashboard(opens in a new tab) to pay your AWS bill, monitor your usage, and analyze and control your costs.

Compare your current month-to-date balance with the previous month, and get a forecast of the next month based on current usage.
- View month-to-date spend by service.
- View Free Tier usage by service.
- Access Cost Explorer and create budgets.
- Purchase and manage Savings Plans.
- Publish AWS Cost and Usage Reports(opens in a new tab).

---
### Consolidated Billing
Consolidated billing is a feature for AWS Organizations that enables you to receive a single bill for all AWS accounts in your organization. 

The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.

Benefits of consolidated billing:
1. You can still review itemized charges incurred by each aacount which enables you to have greater transparency into your organization's accounts while still maintaining the convenience of receiving a single monthly bill.
2. To share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in your organization. For instance, one account might not have enough monthly usage to qualify for discount pricing. However, when multiple accounts are combined, their aggregated usage may result in a benefit that applies across all accounts in the organization.

---
### AWS Budgets
In AWS Budgets(opens in a new tab), you can create budgets to plan your service usage, service costs, and instance reservations.

The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.

In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

---
### AWS Cost Explorer
AWS Cost Explorer(opens in a new tab) is a tool that lets you visualize, understand, and manage your AWS costs and usage over time.

AWS Cost Explorer includes a default report of the costs and usage for your top five cost-accruing AWS services. You can apply custom filters and groups to analyze your data. For example, you can view resource usage at the hourly level.

--- 
### AWS Support Plans
AWS offers four different Support plans(opens in a new tab) to help you troubleshoot issues, lower costs, and efficiently use AWS services. 

1. Basic
2. Developer
3. Business 
4. Enterprise On-Ramp
5. Enterprise
Each support plan is build on the previous one. E.g. Enterprise support plan includes Enterprise On-Ramp and additional features. This same goes with Enterprise On-Ramp, it includes Business Support Plan and additional features.

#### Basic Support
Basic Support is free for all AWS customers. 

It includes
- whitepapers 
- documentation, and 
- support communities. 
- you can also contact AWS for billing questions and service limit increases.
- you have access to a limited selection of AWS Trusted Advisor checks.
- you can use the **AWS Personal Health Dashboard**, a tool that provides alerts and remediation guidance when AWS is experiencing events that may affect you. 

#### Developer, Business, Enterprise On-Ramp, and Enterprise Support
including all the benefits of Basic Support, in addition to the ability to open an unrestricted number of technical support cases. These Support plans have pay-by-the-month pricing and require no long-term contracts.

##### Developer Support
Customers in the Developer Support plan have access to features such as:

- Best practice guidance
- Client-side diagnostic tools
- Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together

##### Business Support
Customers with a Business Support plan have access to additional features, including: 

- Use-case guidance to identify AWS offerings, features, and services that can best support your specific needs
- All AWS Trusted Advisor checks
- Limited support for third-party software, such as common operating systems and application stack components

##### Enterprise On-Ramp Support
 In addition to all the features included in the Basic, Developer, and Business Support plans, customers with an Enterprise On-Ramp Support plan have access to:

- A pool of Technical Account Managers to provide proactive guidance and coordinate access to programs and AWS experts
    - Consultative review and architecture guidance (one per year)
    - Infrastructure Event Management support (one per year)
    - Support automation workflows
    - 30 minutes or less response time for business-critical issues
- A Cost Optimization workshop (one per year)
- A Concierge support team for billing and account assistance
- Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard

##### Enterprise Support
In addition to all features included in the Basic, Developer, Business, and Enterprise On-Ramp support plans, customers with Enterprise Support have access to:

- A designated Technical Account Manager to provide proactive guidance and coordinate access to programs and AWS experts
    - Consultative review and architecture guidance
    - Infrastructure Event Management support
    - Cost Optimization Workshop and tools
    - Support automation workflows
    - 15 minutes or less response time for business-critical issues
- A Concierge support team for billing and account assistance
- Operations Reviews and tools to monitor health
- Training and Game Days to drive innovation
- Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard

#### Technical Account Manager (TAM)
The Enterprise On-Ramp and Enterprise Support plans include access to a Technical Account Manager (TAM).

The TAM is your primary point of contact at AWS. If your company subscribes to Enterprise Support or Enterprise On-Ramp, your TAM educates, empowers, and evolves your cloud journey across the full range of AWS services. TAMs provide expert engineering guidance, help you design solutions that efficiently integrate AWS services, assist with cost-effective and resilient architectures, and provide direct access to AWS programs and a broad community of experts.

---
### AWS Marketplace