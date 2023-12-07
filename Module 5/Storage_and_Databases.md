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
- Data store as objects in the bucket (it's like file in the directory, although the bucket isn't a directory)
    - Oject consists of data, metadata, and a key.
    - The key is the FULL path (prefix + object name):
        - s3://my-bucket/my_file.txt
        - s3://my-bucket/my_folder/another_folder/my_file.txt
    - Object values are the content of the body
    - Metadata are a list of text of key-values pairs
- Amazon S3 offers unlimited storage space
- The maximum file size for an object in Amazon S3 is 5TB. If a file is more than 5GB, must use "multi-part upload"
- Can set permissions to control visibility and access to it.
- Can also use the Amazon S3 versioning feature to track changes of objects over time.
- When choosing an storage class, two factors is considered:
    - How often you plan to retrieve your data ?
    - How available you need your data to be ? 
- Amazon S3 storage classes:
    1. **S3 Standard**
        - Used for frequently accessed data
        - Low latency and high throughput
        - Can sustain 2 concurrent facility failures
        - Use cases: Big Data analytics, mobile & gaming applications, content distribution

    2. **S3 Standard-Infrequent A (S3 Standard-IA)**
        - For data that's less frequently accessed, but requires rapid access when needed
        - Lower cost than S3 Standard
        - use cases: Disaster Recovery, backups

    3. **S3 One Zone-Infrequent Access (S3 One Zone-IA)**
        - High durability in a single AZ; data lost when AZ is destroyed
        - 99.5% availability (Lower availability)
        - use cases: storing secondary backup copies of on-premise data, or data that you can recreate

    4. **S3 Intelligent-Tiering**
        - Moves objects automatically between Access Tiers based on usage
        - Small monthly monitoring and auto-tiering fee
        - No retrieval charges in S3 intelligent-Tiering
        - Different tiers:
            - Frequent Access tier (automatic): default tier
            - Infrequent Access tier (automatic): objects not accessed for 30 days
            - Archive Access tier (automatic): objects not accessed for 90 days
            - Archive Access tier (optional): configurable from 90 days to 700+ days
            - Deep Archive Access tier (optimal): config from 180 days to 700 days
        
    5. **S3 Glacier Instant Retrieval**
        - Low-cost object storage meant for archiving/ backup
        - Pricing: price for storage + object retrieval cost
        - Millisecond retrieval, great for data accessed once a quarter
        - Minimum storage duration of 90 days

    6. **S3 Glacier Flexible Retrieval**
        - Low-cost object storage meant for archiving/ backup
        - Pricing: price for storage + object retrieval cost
        - Expedited (1 to 5 minutes), Standard (3 to 5 hours), Bulk(5 to 12 hours)[Free]
        - Minimum storage duration of 90 days

    7. **S3 Glacier Deep Archive**
        - Low-cost object storage meant for archiving/ backup
        - Pricing: price for storage + object retrieval cost
        - For long term storage
        - Standard (12 hours), Bulk(48 hours)
        - Minimum Duration of 180 days

    8. **S3 Outposts**
        - Creates S3 buckets on Amazon S3 Outposts
        - Makes it easier to retrieve, store, and access data on AWS Outposts
- Can move between classes manually or using S3 Lifecycle configuration
- S3 Durability && Availability 
    - Durability 
        - AWS S3 is high durability (99.999999999%, 11 9's) of objects across multiple AZ
        - Same for all storage classes
    - Availability
        - Varies depending on the storage class


---
### Block storage vs Object storage

| Object Storage | Block Storage |
|----------------|---------------|
|- Object storage treats any file as a complete, discreet object. Now this is great for documents, and images, and video files that get uploaded and consumed as entire objects, but every time there's a change to the object, you must re-upload the entire file. There are no delta updates. | - Block storage breaks those files down to small component parts or blocks. This means, for that 80-gigabyte file, when you make an edit to one scene in the film and save that change, the engine only updates the blocks where those bits live. |
---
### Comparing Amazon EBS and Amazon S3

When it comes to choose which storage service to use, it depends on the use case.

| S3 | EBS |
|----|-----|
| - Objects storgae     | - Block storage                                 |
| - Using complete objects  | - Use for complex read, write, change functions |
| - Only occasional changes |                                                 |

---
### Amazon Elastic File System (Amazon EFS)
In file storage, multiple clients can access data that is stored in shared file folders. 
In this approach, a storage server uses block storage with a local file system to organize files. 
Clients access data through file paths.

Compared to block storage and object storage, file storage is ideal for use cases in which a large number of services and resources need to access the same data at the same time.

Amazon Elastic File System (Amazon EFS)(opens in a new tab) is a scalable file system used with AWS Cloud services and on-premises resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications. 

---
### AWS Storage Cloud Native Options

| Block storage        | File storage | Object storage |
| ---------------------|--------------|----------------|
| - EBS                | - EFS        | - S3           |
| - EC2 instance store |              | - Glacier      |

**AWS Storage Gateway**
 - Bridging between on-premise data and cloud data
 - Hybrid storage service to allow on-premises to seamlessly use AWS Cloud.

---
### AWS Relationship Database Service 
In a relational database, data is stored in a way that relates it to other pieces of data. 
Relational databases use structured query language (SQL) to store and query data. This approach allows data to be stored in an easily understandable, consistent, and scalable way. 

Amazon Relational Database Service (Amazon RDS)(opens in a new tab) is a service that enables you to run relational databases in the AWS Cloud.
Amazon RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups.
Amazon RDS provides a number of different security options. Many Amazon RDS database engines offer encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received).

**Amazon RDS database engines**
Amazon RDS is available on six database engines, which optimize for memory, performance, or input/output (I/O). Supported database engines include:

- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

---
### Amazon DynamoDB
In a nonrelational database, you create tables. A table is a place where you can store and query data.

Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. One type of structural approach for nonrelational databases is key-value pairs. With key-value pairs, data is organized into items (keys), and items have attributes (values). You can think of attributes as being different features of your data.
In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes. 

**Amazon DynamoDB**
Amazon DynamoDB(opens in a new tab) is a key-value database service. It delivers single-digit millisecond performance at any scale.
- serverless
    DynamoDB is serverless, which means that you do not have to provision, patch, or manage servers. 
    You also do not have to install, maintain, or operate software.
- automatic scaling
    As the size of your database shrinks or grows, DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance. 

---
### Comparing AmaZon RDS and DynamoDB

| RDS | DynamoDB |
|-----|----------|
| - automatic high availability and recovery provided | - able to operate as a global database at the touch of a button |
| - You control the data, you control the schema, you control the network. | -  It has massive throughput. It has petabyte scale potential. It has granular API access. |

---
### Amazon Redshift
Amazon Redshift(opens in a new tab) is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data. This service is beneficial for big data historical anaylitics.

---
### Amazon Database Migration Service
AWS Database Migration Service (AWS DMS)(opens in a new tab) enables you to migrate relational databases, nonrelational databases, and other types of data stores.

With AWS DMS, you move data between a source database and a target database. The source and target databases(opens in a new tab) can be of the same type or different types. During the migration, your source database remains operational, reducing downtime for any applications that rely on the database. 

For example, suppose that you have a MySQL database that is stored on premises in an Amazon EC2 instance or in Amazon RDS. Consider the MySQL database to be your source database. Using AWS DMS, you could migrate your data to a target database, such as an Amazon Aurora database.

Other use cases for AWS DMS:
1. Development and test database migrations
    Enabling developers to test applications against production data without affecting production users
2. Database consolidation
    Combining several databases into a single database
3. Continuous replication
    Sending ongoing copies of your data to other target sources instead of doing a one-time migration

---
### Additional Database service

There's no one-size-fits-all database.

1. Amazon DocumentDB
    a document database service that supports MongoDB workloads.
2. Amazon Neptune
    a graph database service to build and run applications that work with highly connected datasets
3. Amazon Quantum Ledger Database (Amazon QLDB)
    a ledger database service to review a complete history of all the changes that have been made to your application data.
4. Amazon Managed Blockchain
    to create and manage blockchain networks with open-source frameworks. 
5. Amazon ElastiCache
    adds caching layers on top of your databases to help improve the read times of common requests. 
6. Amazon DynamoDB Accelerator (DAX) 
    an in-memory cache for DynamoDB that helps improve response times from single-digit milliseconds to microseconds.

---