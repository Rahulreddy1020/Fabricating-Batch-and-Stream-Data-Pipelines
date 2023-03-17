# Fabricating-Batch-and-Stream-Data-Pipelines

## Business Overview :
Ecommerce analytics is the process which involves gathering data from various sources to analyze customer behavior and shopping patterns across the entire customer journey. In this project, an eCommerce dataset will be used to create two analytical pipelines: Batch and Real-time. The Batch processing involves ingesting, processing, and visualizing data using various Amazon services to draw insights such as 
- unique visitors per day 
- identifying when users add products to carts but don't buy 
- top categories per hour/weekday for promotions, and identifying brands that need more marketing. 

On the other hand, the Real-time channel focuses on detecting Distributed Denial of Service (DDoS) and Bot attacks using AWS Lambda, DynamoDB, CloudWatch, and AWS SNS.
     
## Dataset Description :

This dataset contains user behavioral information from a large multi-category online store along with fields such as event_time, event_type, product_id, price, user_id. Each row in the file represents one of the following event types such as View,Cart,Removed from Cart,Purchase. the data is extracted from the following link https://rees46.com/en/open-cdp

## Tech Stack:
#### Languages : 
     Python
     SQL
#### AWS Services :
     AWS S3
     AWS Glue
     AWS Athena
     AWS Cloud9
     Apache Flink
     Amazon Kinesis
     Amazon SNS
     AWS Lambda
     Amazon CloudWatch
     QuickSight
     Apache Zepplin
     Amazon DynamoDB
     
## System Architecture 

Below is the lucid chart diagram of system architecture. after we downloaded the data in CSV format, we have stored this data in s3 bucket which is a data lake service. 

later we lauched a cloud 9 in EC2 instance to run boto3 to connect python simulator to AWS services.

Now we had to create a Kinesis streams which could handle our continous streaming data, this will be our stream 1.

the python simulator is created in such a way it connects to s3 bucket to pull the static data which is in CSV and simulates it into a continous stream with partitions based on Category Id, here we will shard the data in Kinesis streams with category id.

The glue service is used now to crawl the data from Stream 1


  
![image](https://user-images.githubusercontent.com/83365184/222992271-4c3f3f06-fb32-4664-9968-b52d5ba93a34.png)

## Implementation

## S3 

The data which is in CSV format is moved to Amazon Simple Storage Service Bucket, since most of the this project is associated with aws services, also it is a cheap cloud storage provider.

Amazon S3 (Simple Storage Service) is a cloud-based object storage service provided by Amazon Web Services (AWS). S3 enables users to store and retrieve any amount of data, at any time, from anywhere on the web. It provides a highly scalable, reliable, and cost-effective storage infrastructure that can be used for a wide range of use cases, such as backup and restore, disaster recovery, archiving, data lakes, and big data analytics.

S3 stores objects (files) in buckets, which are containers for objects that can be accessed using a unique URL. S3 supports multiple storage classes, including Standard, Standard-Infrequent Access (IA), One Zone-Infrequent Access (One Zone-IA), Intelligent Tiering, Glacier, and Glacier Deep Archive. Each storage class has different features, performance characteristics, and costs, allowing users to choose the appropriate storage class for their specific use case and data access requirements.

## Cloud9 

To run our python script which has been created to mimic the real time data, we will be using cloud9.

Cloud9 is an integrated development environment (IDE) that allows developers to write, run, and debug code in the cloud. It is a web-based platform that is fully managed by AWS and provides a range of features, such as code editing, debugging, collaboration, and more.

To use Cloud9 in AWS, you will need an AWS account. Once you have an AWS account, you can create a Cloud9 environment by following these steps:

Go to the AWS Management Console and select the Cloud9 service.
Click on the "Create environment" button.
Give your environment a name and select the type of environment you want to create (for example, a Python in our case).
Choose the settings for your environment, such as the instance type, network settings, and permissions.
Click on the "Create environment" button to create your environment.
Once your environment is created, you can start writing and running code in the cloud using the Cloud9 IDE. You can also collaborate with other developers by sharing your environment with them.

Cloud9 in AWS provides a powerful and flexible development environment that can help you streamline your development workflows and accelerate your development process

## Boto3

Boto3 needs to be installed in cloud9 to connect our python script to aws services.

Boto3 is a Python software development kit (SDK) for AWS (Amazon Web Services) that enables developers to create Python scripts or applications to interact with AWS services. Boto3 provides an easy-to-use, Pythonic interface to AWS services, making it simple to integrate AWS into your Python applications.

Using Boto3, developers can create, configure, and manage AWS resources like EC2 instances, S3 buckets, RDS instances, and more programmatically. Boto3 provides Pythonic methods for interacting with AWS resources, making it easy to integrate AWS services with Python applications.

Boto3 also supports automatic credential management, allowing you to authenticate and authorize access to AWS services using AWS Identity and Access Management (IAM) roles, profiles, or environment variables.

With Boto3, developers can easily build serverless applications using AWS Lambda functions, which can be triggered by events from various AWS services like S3, Kinesis, DynamoDB, and more. Boto3 also supports AWS Step Functions, enabling developers to create and manage state machines that coordinate AWS services.

!

![image](https://user-images.githubusercontent.com/83365184/222992656-74222c6d-496b-4e43-8fc7-2114bde0bbee.png)

![image](https://user-images.githubusercontent.com/83365184/222992678-2b29bb90-2c90-4578-92f2-6d0da154ee0f.png)








   
                                      

