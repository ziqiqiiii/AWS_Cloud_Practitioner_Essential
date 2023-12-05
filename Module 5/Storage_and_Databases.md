# Storage and Databases

---

- [X] Summarize the basic concept of storage and databases.
- [X] Describe the benefits of Amazon Elastic Block Store (Amazon EBS).
- [X] Describe the benefits of Amazon Simple Storage Service (Amazon S3).
- [X] Describe the benefits of Amazon Elastic File System (Amazon EFS).
- [X] Summarize various storage solutions.
- [X] Describe the benefits of Amazon Relational Database Service (Amazon RDS).
- [X] Describe the benefits of Amazon DynamoDB.
- [X] Summarize various database services.

---
| Storage services | Database services                |
|:----------------:|:--------------------------------:|
| - EBS            | - RDS                            |
| - S3             | - DynamoDB                       |
| - EFS            | - Redshift                       |
|                  | - AWS Database Migration service |
|:-----------------|:---------------------------------|
---

When running EC2, it stores its data temporary locally on instance store, a block-level storage volumes behave like physical hard drives.
An instance store is disk storage that's physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance.
When instance is terminated, users lose any data in the instance sore.

---