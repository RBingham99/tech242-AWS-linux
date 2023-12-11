# AWS Basics

# What is AWS?
Amazon Web Services (AWS) is a comprehensive and widely used cloud computing platform provided by Amazon. It offers a vast array of services, catering to various computing, storage, database, machine learning, analytics, security, and other business needs.

# What does AWS provide?
- Compute Services:
Amazon EC2 (Elastic Compute Cloud): Provides scalable compute capacity in the cloud, allowing users to run virtual servers for various applications.
Amazon Lambda: A serverless compute service that automatically scales and executes code in response to events without the need to provision or manage servers.

- Storage Services:
Amazon S3 (Simple Storage Service): Offers scalable object storage for data storage and retrieval. It is widely used for hosting static websites, backup, and data archiving.
Amazon EBS (Elastic Block Store): Provides persistent block-level storage volumes for use with Amazon EC2 instances.

- Database Services:
Amazon RDS (Relational Database Service): Manages relational databases such as MySQL, PostgreSQL, and Oracle. It automates routine database tasks.
Amazon DynamoDB: A NoSQL database service that delivers fast and predictable performance with seamless scalability.

- Networking:
Amazon VPC (Virtual Private Cloud): Allows users to provision a logically isolated section of the AWS Cloud where they can launch AWS resources in a virtual network.

- Security and Identity:
AWS IAM (Identity and Access Management): Enables users to securely control access to AWS services and resources.
AWS Key Management Service (KMS): Helps manage encryption keys and control access to encrypted data.

- Machine Learning and AI:
Amazon SageMaker: A fully managed service for building, training, and deploying machine learning models.
Amazon Polly: Converts text into lifelike speech using deep learning.

- Analytics and Big Data:
Amazon Redshift: A fully managed data warehouse that enables users to analyze large datasets with high performance and scalability.
Amazon EMR (Elastic MapReduce): A cloud-based big data platform for processing and analyzing vast amounts of data using popular frameworks like Apache Spark and Hadoop.

- Developer Tools:
AWS CodeDeploy: Automates code deployments to any instance, including Amazon EC2 instances and on-premises servers.
AWS CodePipeline: A continuous integration and continuous delivery (CI/CD) service for fast and reliable application updates.

- Management and Monitoring:
AWS CloudWatch: Monitors AWS resources and applications in real-time, and can automatically respond to defined events.
AWS CloudTrail: Records AWS API calls for auditing, compliance, and troubleshooting.

- Serverless Computing:
AWS Step Functions: Coordinates the components of distributed applications using visual workflows.
AWS SAM (Serverless Application Model): An open-source framework for building serverless applications.

My take-away from this is that AWS can provide a vast array of services and you should consider which you will need.

# AWS regions and availability zones

- AWS Regions are separate geographic areas.

- AWS Regions consist of multiple, physically separated and isolated Availability Zones that are connected with low latency, high throughput and highly redundant networking.

- These Availability Zones enable you to operate production applications and databases that are more highly available, fault tolerant, and scalable than possible when using a single data center. You can deploy your applications and databases across multiple Availability Zones. In the unlikely event of a failure of one Availability Zone, user requests are routed to your application instances in the second Availability Zone. This approach ensures that your application continues to remain available at all times.

![Alt text](../../readme-images/AWS-regions-and-zones.png)

My take-away from this is that AWS regions and availability zones are a great idea as it allows users to deploy applications and know that even if there is an issue with 1 data centre it will not cause an issue for your application.

# How AWS points of presence work
When a user requests data or an object in your application, the request goes from the client to the AWS servers and back to the user.
![AWS-pop-diagram](../../readme-images/AWS-pop-diagram.avif)<br>
In the scenario above, our website "example.com" uses a CloudFront Distribution to deliver our data to our users. This is what happens next:

1) The user opens your website and requests an object like an HTML file.

2) The CloudFront URL/DNS routes the request to the nearest CloudFront Point of Presence (PoP or edge location)

3) The Edge Location cache is checked.

4) If the object is in the cache, CloudFront returns it.

5) If the object is not in the cache, CloudFront forwards the request to your server (CloudFront Origin).

6) The server returns the data to the edge location.

7) CloudFront forwards the data to the user and adds it to the cache. For subsequent requests, the data is returned from the cache.

My take-away from this is that AWS points of presence is very useful as it means that a request for data may not need to go all the way to the server if the data is cached at the PoP, meaning you will get the data faster.