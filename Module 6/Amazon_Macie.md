# Amazon Macie

Amazon Macie is a fully managed data security and data privacy service that uses machine learning and pattern matching to discover and protect your sensitive data in AWS. Macie automatically provides an inventory of Amazon S3 buckets including a list of unencrypted buckets, publicly accessible buckets, and buckets shared with AWS accounts outside those you have defined in AWS Organizations. Then, Macie applies machine learning and pattern matching techniques to the buckets you select to identify and alert you to sensitive data, such as personally identifiable information (PII).

How Macie Works:
1. Enable Amazon Macie with one-click in the AWS Management Console or a single API call
2. Continually evaluate your S3 environment
    - Automatically generates an inventory of S3 buckets and details on the bucket-level security and access controls
3. Discover sensitive data
    - Analyzes buckets using machine learning and pattern matching to discover sensitive data, such personally identifiable information (PII)
4. Take actions
    - Generate findings and sends to Amazon CloudWatch Events for integration into workflows and remediation actions.
    