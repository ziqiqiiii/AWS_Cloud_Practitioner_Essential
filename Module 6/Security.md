# Security
---
- [X] Explain the benefits of the shared responsibility model.
- [X] Describe multi-factor authentication (MFA).
- [X] Differentiate between the AWS Identity and Access Management (IAM) security levels.
- [X] Explain the main benefits of AWS Organizations.
- [X] Describe security policies at a basic level.
- [X] Summarize the benefits of compliance with AWS.
- [X] Explain additional AWS security services at a basic level.
---
### Share responsibility 

AWS       - responsible for security on the cloud
Customers - responsible for security in the cloud 

|AWS            | Customers             |
|---------------|-----------------------|
| - Software    | - Customer Data 
| - Compute, storage, database, networking | - Platform, Application, Identity, and Access Management |
| - Hardware/AWS Global Infrastructure | - OS, Network, and Firewall configuration |
| - Regions, AZs, Edge locations | Client-side data encryption, server-side encryption, networking traffic protection |

--- 
### AWS Identity Access Management (IAM)

#### AWS account root user 
When you first create an AWS account, you begin with an identity known as the root user(opens in a new tab). 

#### IAM users
An IAM user is an identity that you create in AWS. It represents the person or application that interacts with AWS services and resources. It consists of a name and credentials.

- By default, when you create a new IAM user in AWS, it has no permissions associated with it

#### IAM policies
An IAM policy is a document that allows or denies permissions to AWS services and resources.  

- IAM policies enable you to customize users’ levels of access to resources. 
- For example, you can allow users to access all of the Amazon S3 buckets within your AWS account, or only a specific bucket.
- Follow the security principle of least privilege when granting permissions.

#### IAM groups
An IAM group is a collection of IAM users. When you assign an IAM policy to a group, all users in the group are granted permissions specified by the policy.

- e.g.  Instead of assigning permissions to cashiers one at a time, the owner can create a “Cashiers” IAM group. The owner can then add IAM users to the group and then attach permissions at the group level. 

#### IAM roles
An IAM role is an identity that you can assume to gain temporary access to permissions.  

- Before an IAM user, application, or service can assume an IAM role, they must be granted permissions to switch to the role. When someone assumes an IAM role, they abandon all previous permissions that they had under a previous role and assume the permissions of the new role. 

#### Multi-factor authentication (MFA)
In IAM, multi-factor authentication (MFA) provides an extra layer of security for your AWS account.

- First, a user enters thier IAM user ID and password to sign in to an AWS website. next, the user is prompted for an authentication response from their AWS MFA device. This device could be hardware security key, a hardware device, or an MFA application on a device. When the user has been successfully authenticated, they are able to access the requested AWS services or resources. 
- You can enable MFA for the root user and IAM users. 
- As a best practice, enable MFA for the root user and all IAM users in your account. By doing this, you can keep your AWS account safe from unauthorized access.

--- 
### AWS Organizations
To consolidate and manage multiple AWS accounts within a central location.

Benefits
- Centralized management 
- Consolidated biling
- Hierarchical groupings of accounts
- AWS service and API actions access control

In AWS Organizations, you can centrally control permissions for the accounts in your organization by using service control policies (SCPs)(opens in a new tab). SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

In AWS Organizations, you can group accounts into organizational units (OUs) to make it easier to manage accounts with similar business or security requirements. When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy. 

---
### Compliance

#### AWS Artifact
AWS Artifact(opens in a new tab) is a service that provides on-demand access to AWS security and compliance reports and select online agreements. 

AWS Artifact consists of two main sections: AWS Artifact Agreements and AWS Artifact Reports.
1. AWS Artifact Agreements
   Companies that need to sign an agreement with AWS regarding your use of certain types of information throughout AWS services. 
   In AWS Artifact Agreements, you can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations. Different types of agreements are offered to address the needs of customers who are subject to specific regulations

2. AWS Artifact Reports
    AWS Artifact Reports provide compliance reports from third-party auditors. These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific security standards and regulations. AWS Artifact Reports remains up to date with the latest reports released. You can provide the AWS audit artifacts to your auditors or regulators as evidence of AWS security controls. 

#### Customer Compliance Center
The Customer Compliance Center(opens in a new tab) contains resources to help you learn more about AWS compliance.

In the Customer Compliance Center, you can read customer compliance stories to discover how companies in regulated industries have solved various compliance, governance, and audit challenges.

You can also access compliance whitepapers and documentation on topics such as:

AWS answers to key compliance questions
An overview of AWS risk and compliance
An auditing security checklist
Additionally, the Customer Compliance Center includes an auditor learning path. This learning path is designed for individuals in auditing, compliance, and legal roles who want to learn more about how their internal operations can demonstrate compliance using the AWS Cloud.

---
### Denial-of-Service Attacks
#### Denial-of-Service Attacks
A denial-of-service (DoS) attack is a deliberate attempt to make a website or application unavailable to users.

#### Distributed denil-of-service attacks
A single threat actor targets a website or application from multiple sources.

#### AWS Shield
AWS Shield is a service that protects applications against DDoS attacks. 

AWS Shield provides two levels of protection: Standard and Advanced.
1. AWS Shield Standard
    AWS Shield Standard automatically protects all AWS customers at no cost. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks. 

    As network traffic comes into your applications, AWS Shield Standard uses a variety of analysis techniques to detect malicious traffic in real time and automatically mitigates it. 
2. AWS Shield Advanced
    AWS Shield Advanced is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. 

    It also integrates with other services such as Amazon CloudFront, Amazon Route 53, and Elastic Load Balancing. Additionally, you can integrate AWS Shield with AWS WAF by writing custom rules to mitigate complex DDoS attacks.

    ---