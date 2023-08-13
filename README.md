# Fabricating-Batch-and-Stream-Data-Pipelines

## Problem Statement

An eCommerce company has received requests from the marketing team and Datascience team to build a real-time data pipeline that can analyze the shopping journey and behavior of users as well as detect any anomalies or intrusions on the website.

-Marketing team wants to analyze user shopping journey in real-time.
-Data Science team wants to detect anomalies on the website in real-time.
-The pipeline must involve ingesting, processing, and visualizing data simultaneously & must be capable of detecting anomalies or intrusions on website.
-The pipeline will be deployed to a production environment where Regular monitoring and maintenance are required.

## Goals

- We will be analyzing the realtime stream data for making realtime decisions
- Detecting the intusions on the website and sending an alarm or Notifications
## Business Overview :
Ecommerce analytics is the process which involves gathering data from various sources to analyze customer behavior and shopping patterns across the entire customer journey. In this project, an eCommerce dataset will be used to create two analytical pipelines using various Amazon services to draw insights such as 

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

Below is the lucid chart diagram of system architecture. 

the python simulator is created in such a way it connects to s3 bucket to pull the static data which is in CSV and simulates it into a continous stream with shards based on Category Id.



  
![image](https://user-images.githubusercontent.com/83365184/222992271-4c3f3f06-fb32-4664-9968-b52d5ba93a34.png)

