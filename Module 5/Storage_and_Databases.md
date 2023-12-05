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
---
### How EC2 store its data 

When running EC2, it stores its data temporary locally on instance store, a block-level storage volumes behave like physical hard drives.
An instance store is disk storage that's physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance.
When instance is terminated, users lose any data in the instance sore.

---
### Amazon Elastic Block Store (Amazon EBS)

- A service that provides block-level storage volumes that you can use with Amazon EC2 instances. If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.
- To creat an EBS volume, user have to define:
    - Volume size
    - Type
- After EBS is created, it an be attach to an Amazon EC2 instance.
- Take incremental backups of EBS volumes by taking snapshots
- Characteristics of EBS:
    - Best for data that requires retention
    - Separate drives from the host computer of an EC2 instance

---
### Amazon Simple Storage Service (S3)

Amazon Simple Storage Service (Amazon S3)(opens in a new tab) is a service that provides object-level storage. Amazon S3 stores data as objects in buckets.

- Any type of file can be uploaded to Amazon S3:
    - images, videos, text files
- Amazon S3 offers unlimited storage space
- The maximum file size for an object in Amazon S3 is 5TB
- Can set permissions to control visibility and access to it.
- Can also use the Amazon S3 versioning feature to track changes of objects over time.
- When choosing an storage class, two factors is considered:
    - How often you plan to retrieve your data ?
    - How available you need your data to be ? 
- Amazon S3 storage classes:
    1. **S3 Standard**
    2. **S3 Standard-Infrequent A (S3 Standard-IA)**
    3. **S3 One Zone-Infrequent Access (S3 One Zone-IA)**
    4. **S3 Intelligent-Tiering**
    5. **S3 Glacier Instant Retrieval**
    6. **S3 Glacier Flexible Retrieval**
    7. **S3 Glacier Deep Archive**
    8. **S3 Outposts**

---

### Comparing Amazon EBS and Amazon S3