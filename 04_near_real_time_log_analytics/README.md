# Near Real-Time Log Analytics

![ScreenShot](/assets/images/044.png)

This project aims to produce a near real-time log analytics system using AWS services to gain immediate insights from log data. The solution leverages Kinesis Firehose and OpenSearch to process and analyze log data in near real-time.

**Use Case:** We get a pre-configured notification that tells us there are currently extremely high traffic volumes on our Cadabra website. It could be an attack on our system, so we'll want to act quickly. This implementation gives us the investigative tools to discover what is happening in real time.

## Steps in the Implementation

### 1. Data Ingestion from Kinesis stream
Steps have been previously implemented in the `01_order_history_functionality` folder.

We're simply connecting our Kinesis data stream to the Kinesis Firehose delivery stream.

### 2. Firehose Delivery Stream

Be sure to configure the lambda function to transform data coming into Firehose - convert log to JSON (there are lambda blueprints), and increase lambda timeout to one minute. 


### 3. Data Visualization with OpenSearch

In OpenSearch, you should partition the logs by day. After that, make a cluster to receive log data from the Kinesis Firehose.


## Prerequisites

Before setting up and running this implementation, ensure that you have:

- AWS account credentials with appropriate permissions to create and manage Kinesis Firehose.

- Familiarity with SQL queries.

