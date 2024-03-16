# Data and ML

## Glue
* Serverless ETL service
* Features centralized data catalog a persistence metadata store for assets
* Automatic schema discovery
* Visual ETL Job authoring
* Crawler crawls the datastore to populate the Glue catalogs
* Data source > Extract > Transform data using a script > Load > Data Target
* Use case - Import CSV from S3 bucket, covnert to Parquet(Column), output to an S3 bucket and then analyze with Athena
* Glue job bookmarks - stops the processing of old data
* Reference training slides for the rest of topics

# Kinesis
* Add shards to increase scalability
* Real-time streaming ingestion tool
* Video streams
  * Outputs to Rekognition and Sagemaker for video analysis
* Kinesis Data Streams is for building custom real-time data processing applications with fine-grained control, while Kinesis Data Firehose is for easily loading streaming data into AWS data stores and analytics services without managing infrastructure or writing custom code.
* Data streams
  * Multiple shards define your capacity(On-demand or provisioned)
  * 1 ms latency processing (Real time processing)
  * Data storage between 1 - 365 days. This enables data replay
  * Consumers
    * KCL(Kinesis client library), SDK
    * Lambda
    * Kinesis Data Firehose
* Kinesis Data Firehose
  * Producers same as Data streams, plus CloudWatch, Kinesis Data streams, AWS IOT 
  * Takes inputs, uses ETL on the data, and outputs to data warehouses such as S3, Redshift, OpenSearch, and Splunk
  * 60 ms latency, not as real-time as data streams
  * Automatic scaliing
  * No storage
  * No replay
* Kinesis Data analytics
  *  For SQL applications: Use SQL statements on real-time streams from Kinesis Data streams & Firehose
  *  For Apache Flink: Use Java, Scala or SQL to process real-time data
    * Parallel computation, automatic scaling, snapshots as backups
    * Can use with Kinesis Analytics for SQL only - not Firehose

## Amazon MQ
* Managed message broker service for Rabbit MQ and ActiveMQ
* Supports open source brokers
* Not as scalable as SQS
* Uses servers in Multi-AZ for failover (active/standby)

## Athena
* Severless Amazon S3 query service that uses SQL langauge
* Used with Amazon Quicksight for reporting and dashboards
* Supports CSV, JSON and Parquet
* Used for BI, analytics, VPC Flow Logs, ELB logs, CloudTrail trails
* Performance and cost savings
  * Columnar for cost saving - less scans
  * Apache Parquet or ORC recommended
  * Large perform improvement
  * Compress data to create smaller retrievals
  * Partition the datasets in S3
  * User larger files
* Federated Query
  * Can run SQL queries accross different data sources
  * Use data connectors that run on Lambda - Query CloudWatch logs, DynamoDB, RDS etc...
  * Results are stored back in S3
## EMR
* Creates Hadoop clusters for big data analysis of large amounts of data
* Clusters are made up of hundreds of EC2 instances
* Big data processing with Apache Spark, HBase Presto, Flink
* Master and core nodes are long running
* Task nodes just run task - spot instances

## QuickSite
* Serverless ML BI service for creating dahsboards
* Integrates with Athena and Redshift

## AWS Lake Formation
* Data lake - central location for all analytics data
* Can combine structured and unstructured data
* Out of the box blueprints: S3, RDS,NoSQL and Relational DB
* Fine grained access control at the row and column level
* Built on AWS Glue
* Data Lake is stored in S3
* Allows you to centralize permissions between multiple sources

## Amazon Managed Streaming for Apache Kafka (Amazon MSK)
* Alternative to Amazon Kinesis
* Fully managed Apache Kafka
* Data is stored on EBS volumes for an unlimited time
* MSK serverless is an option
* It runs open-source versions of Apache Kafka
* Consumers - Kinesis Data Analytics for Apache Flink, AWS Glue, Lambda, Customer applications(EC2, ECS, EKS)
