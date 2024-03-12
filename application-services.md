# Application Services

## SNS
Problem statement - SNS allows you to decouple your application communications and react to changes. For example trigger an event when a file is uploaded to an S3 bucket

* Enables applications, users and services to send and received notifications
  * Publishers - aplicaiton or AWS services that send messages to topics
  * Messages - app-to-app Lamba, SQS HTTP endpoints or app-to-person push notifications to mobile apps and email addresses
  * Topics - access points where publishers send messages asynchronous
  * Subscribers - subscribe to SNS topics
* Standard topic - Messages do not show up in order, maximum bandwidth, can have duplicates,
* FIFO topic - strict ordering, 300 messages per second
* JSON is the supported data type
* SNS messages are stored accross multiple AZs


## SQS
Problem statement - Sequential proccesing between multiple services can cause bottle necks if one service in the chain is slow. 
SQS is a managed queing service that allows developers decouple communications between distributed workloads such as microservices.

* SQS can be 256KB in size.
* Default retention is 4 days, max is 14 days
* * Messages persist in the queue until a consumer deletes it or the retention period ends
* The visibility timeout id the unavailable time after a message is being processed.
* Each message is deleted after it's processed.
* Dead letter queue isolates and contains messages that failed to be processed
* Can be Standard or FIFO
* Standard queue - best effort ordering, could receive duplicates
* FIFO queue - delivered once, strict ordering, 300 messages or 9000 messages with batching
* Integrates with, Lambda, EC2, S3, Step Functions


## Step Functions
* A service for automating multi step workflows using a GUI
* Orchestrate multiple Lamda functions into a serverless application
* Activity tasks - steps using custom code
* Service tasks - steps using AWS services
* Automates relationship between SNS and SQS
* State machines are designed in JSON
* Express flows - use with high event rates of 100,000 or more and short durations
* Standard flows - use for long running workflows

## AWS Event Bridge
* Salable event bus service that integrates with AWS service along with SaaS services(Shopify, Zendesk etc)
* Event routing and filtering
* Event bus - Location where events are sent
* Rules - control routing to taget applications and services
* Pipes - Filter, enrich, transform data
* Seheduler - configure scheduling patterns.
* Event replay - can replay previous events for troubleshooting
* Schema registry - define shape of your events for other team integrations
* Events can be replicates across multiple regions using global endpoints

## API Gateway
* Simpl
