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
* Data streams
  * Multiple shards define your capacity
  * 1 ms latency processing
  * Consumers
    * KCL(Kinesis client library), SDK
    * Lambda
    * Kinesis Data Firehouse
* Firehouse
  * Takes inputs, uses ETL on the data, and outputs to data warehouses such as S3, Redshift, and Splunk
  * 60 ms latency, not as real-time as data streams
* Data analytics
