# Serverless

## Lambda
* Virutal fucntions - no servers to manage
* Short execution times max of 15 minutes
* Memory between 128 MB and 10GB in 1MB increments
* 512 MB to 10Gb of disk space
* Concurrent execution 1000
* Run on-demand
* Scales automatically
* Pay per request and compute time

# Lambda@Edge
* Edge functions are code that run in a CloudFront distrubtion
* Cloud front functions
  * Written in Java
  * Fast start-up times, millions of reqs/sec
  * Used to change viewer responses and requests
* Lambda@Egde
  * Written in NodeJS or Python
  * Scales to 1000s of requests
  * Max execution time 5 - 10 seconds
  * Creates the function in us-east-1 and replicates to other regions

## Lamda VPC
* Launched in an Amazon owned VPC by default
  * Can access public AWS resources such as S3, DynamoDB

## RDS Invoking Lambda
* You can use RDS events to invoke lambda functions
 * RDS must allow outbound to Lambda via NAT GW, VPC Endpoint etc
 * RDS must have role permissions to call the function
 * RDS events don't have any information about the data itself
  * Must call the functions from within the DB  

## API Gateway
* Supports version
* Support multiple environments
* Handles request throttling
* Transform and validate requests and responses
* Integrates with Lambda nicely

## Amazon Cognito
* Provides user with identity to interact with a web or mobile application
* Integrates with API Gateway and Application Load Balancer
