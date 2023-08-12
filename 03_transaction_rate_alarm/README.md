# Transaction Rate Alarm System

![ScreenShot](/assets/images/03.png)

This project focuses on setting up a transaction rate alarm system using AWS services to monitor transaction rates and trigger alerts when certain thresholds are exceeded.

## Steps in the Implementation

### 1. Data Ingestion from Kinesis stream
Steps have been previously implemented in the `01_order_history_functionality` folder.

We're simply connecting our Kinesis data stream to the Kinesis Firehose delivery stream.

### 2. Real-time Analysis of Incoming Event Logs with Kinesis Analytics

Kinesis Analytics helps us analyze and gain insights from real-time streaming data. It allows us to process continuous data streams using SQL-like queries. We'll set it to check for a high number of log files per hour.

### 3. Data Processing and Trigger Configuration with Lambda

AWS Lambda functions are utilized to process the incoming transaction data. Lambda functions will aggregate, filter, and transform the data to extract the necessary information for calculating transaction rates. We'll also place a trigger here to call our SNS topic.

### 4. SNS Alarm Trigger and Action
Simple Notification Service is a phone alert system; it's activated when triggered by the lambda function. It works simply: A topic is created first - a collective to hold related alerts; then, a subscription is created and set to alert me via an SMS text message.



## Prerequisites

Before setting up and running this implementation, ensure that you have:

- AWS account credentials with appropriate permissions to create and manage Lambda functions, CloudWatch alarms, and other required services.

- Understanding of AWS Lambda, Kinesis Analytics, and CloudWatch services and their integration with other AWS services.
