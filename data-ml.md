# Data and ML

## Glue
* Serverless ETL service
* Features centralized data catalog a persistence metadata store for assets
* Automatic schema discovery
* Visual ETL Job authoring
* Crawler crawls the datastore to populate the Glue catalogs
* Data source > Extract > Transform data using a script > Load > Data Target

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
* Data analytics

## Amazon MQ
  * Managed message broker service for Rabbit MQ and ActiveMQ
  * Supports open source brokers
  * Not as scalable as SQS
  * Uses servers in Multi-AZ for failover (active/standby)
