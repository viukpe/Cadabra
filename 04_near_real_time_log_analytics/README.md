# Near Real-Time Log Analytics

![ScreenShot](/assets/images/044.png)

This project aims to develop a near real-time log analytics system using AWS services to gain immediate insights from log data. The solution leverages Kinesis firehose, and OpenSearch to process and analyze log data in near real-time.

**Use Case:** We get a pre-configured notification that tells us there are currently extremely high traffic volumes on our Cadabra website. This could be an attack on our system and as such we'll want to act quickly. This implementation gives us the investigative tools to find out what is happening in real-time.

## Steps in the Implementation

### 1. Data Ingestion from Kinesis stream
Steps have been previously implemented in the `01_order_history_functionality` folder.

We're simply connecting our Kinesis data stream to the Kinesis Firehose delivery stream.

### 2. Firehose Delivery Stream

Be sure to configure lambda to do data transformation of the data coming into the data stream - log to json(there are lambda blueprints), increase lambda timeout to one minute. Enter OpenSearch service. Index rotation for one day. create backup bucket for bad error logs or all logs. now, setup kinesis agent on ec2, find and open kinesis agent.json file and configure endpoint and flows. Restart your kinesis agent, start log data

### 3. Data Visualization with OpenSearch

Amazon OpenSearch cluster to receive log data, create a domain(basically name)

click opensearch dashboard url link, view manage tab - index patterns(can use to look for log by day) and search for the name you stored your firehose stream as. Go to left menu and click discover

## Prerequisites

Before setting up and running this implementation, ensure that you have:

- AWS account credentials with appropriate permissions to create and manage Kinesis data streams, Kinesis Data Analytics applications, EMR clusters, S3 buckets, and Athena queries.

- Familiarity with SQL queries and big data processing framework - Apache Spark.

