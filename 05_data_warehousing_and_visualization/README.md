# Data Warehousing and Visualization

![ScreenShot](/assets/images/05.png)

Here, we'll focus on the warehousing and visualization components using AWS services. The solution includes Amazon S3 and Redshift for data warehousing, Amazon Glue and Athena for analysis and reporting, and Amazon QuickSight for data visualization.

## Steps in the Implementation

### 1. Data Ingestion from Kinesis stream
Steps have been previously implemented in the `01_order_history_functionality` folder.

We're simply connecting our Kinesis data stream to the Kinesis Firehose delivery stream.

### 2. Data Collection and Storage 

Steps have been previously implemented in the `02_product_recommendations` folder.

We're simply going to use Glue crawlers and Redshift with Spectrum to access the data.

### 2. Data Modeling and Schema Design with Glue

Glue lets us perform crawls on our S3 files to get structure from data by generating a schema for a table. Here we can configure our column names and input types. This table is what we'll later use for Querying and analysis.

![ScreenShot](/assets/images/Glue_table.png)

### 3. Data Analysis and Reporting using Athena

Athena can be integrated with many AWS services, especially Glue, which works seamlessly. It will allow us to quickly run SQL queries on the table we made in Glue. 

![ScreenShot](/assets/images/Athena_small.png)
![ScreenShot](/assets/images/Athena.png)

### 3. Data Transformation and Load into Redshift

Amazon recently introduced a new feature in Redshift called Spectrum, so now we don't need to make a Redshift cluster because we are not storing petabyte-size information, and we already have data on S3. To make a database table, we can create a schema to connect Redshift to our stored data in S3 through our Glue Schema. You should make sure the right IAM policies are attached to your role. 

![ScreenShot](/assets/images/Redshift_table.png)

![ScreenShot](/assets/images/Redshift_fields.png)



### 5. Data Visualization with QuickSight

Amazon QuickSight is a serverless data visualization service that creates interactive dashboards and visualizations based on the analyzed data. QuickSight makes it easy to gain insights through charts, graphs, and other visual elements.

The most critical steps in configuring Quicksight are ensuring your IAM role has the right policies to Read data and ensuring both Quicksight and Redshift are in the same security group. Clusters run in VPC(Virtual Private Clouds), so we'll need a secure connection to read that from it.

![ScreenShot](/assets/images/Quicksight_fields.png)


![ScreenShot](/assets/images/Quicksight_viz.png)


## Prerequisites

Before setting up and running this implementation, ensure that you have:

- AWS account credentials with appropriate permissions to create and manage Redshift clusters, QuickSight dashboards, and other related services.

- Familiarity with SQL queries and data visualization concepts.


