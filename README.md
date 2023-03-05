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

![image](https://user-images.githubusercontent.com/83365184/222992656-74222c6d-496b-4e43-8fc7-2114bde0bbee.png)

![image](https://user-images.githubusercontent.com/83365184/222992678-2b29bb90-2c90-4578-92f2-6d0da154ee0f.png)








   
                                      

