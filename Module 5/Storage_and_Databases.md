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
| - Using complete objects  | - Use for complex read, write, change functions |
| - Only occasional changes |                                                 |

---
### Amazon Elastic File System (Amazon EFS)
