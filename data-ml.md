# Data and ML

## Glue
* Serverless ETL service
* Features centralized data catalog a persistance metadata store for assets
* Automatic schema discovery
* Visual ETL Job authoring
* Crawler crawls the datastore populate the Glue catalogs
* Data source > Extract > Tranform data using a script > Load > Data target

# Kinesis
* Add shards to increase scalability
* Real-time streaming ingestion tool
* Video streams
  * Outputs to Rekognition and Sagemaker for video analysis
* Data streams
  * 1 ms latency processing
* Firehouse
  * Takes inputs, uses ETL on the data, and outputs to data warehouses such as S3, Redshift, and Splunk
  * 60 ms latency, not as real-time as data streams
* Data analytics
