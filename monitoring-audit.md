# Monitoring and Audit

## Amazon CloudWatch Metrics
* Provides metrics for all AWS services
* Metrics belong to namespaces
* Attributes of a metric are called a Dimension
    * Can have to 30 dimensions per metric
* Can create CloudWatch dashboards of metric
* Custom metrics for EC2 RAM for example can collected with the CloudWatch agent
* Can stream CW metrics in near real-time to Amazon Kinesis Data Firehose or third party service

## Amazon CloudWatch Logs
* Can set logs  to expire(1 day to 10 years or never)
* Logs are encrypted by default
* Can use your own keys to setup KMS-Based encryption
* Can sends logs to:
  * Amazon S3
  * Kinesis Data Streams
  * Kinesis Data Firehose
  * AWS Lambda
* S3 exports
  * Can take up to 12 hours for export to become available
  * CreateExportTask is the API call
* Log Subscriptions
  *   Real-time logs events
  *   Send to Kinesis servies or Lambda
  *   Subscription filter - filers logs before they are sent to the destination
* Can sends logs to central account using Cross-Account Subscription features
* By default EC2 instances are not sending logs to CloudWatch
   * The CloudWatch agent is required
   * You need an IAM role with permissions to send logs to CloudWatch
   * Can install agent on on-premises servers as well
   * Unified agent newer and sends RAM and detailed processes information
      * Central configruation using SSM Parameter store 

## CloudWatch Alarms
* Used to trigger alarms on metrics
* Targets - Trigger auto scaling, send notifications to SNS, (stop, terminate, reboot EC2 isntance)
* Composite alarms allow you to combine multiple metrics in a single alarm.

## Amazon EventBridge
* Can schedule Cron jobs
* Can create event rules to react to service changes

## Cloudwatch Insights
* Cloudwatch Container Insights
  * Container metrics and logs
  * ECS,EKS, Fargate needs agents for monitoring Kubernetes
* Cloudwatch Lambda Insights
   * Detailed metrics on serverless applications
* CloudWatch Contributor Insights
   * Find Top N contributors in CloudWatch logs
* CloudWatch Application Insights
   * Automatic dashboards for troubleshooting application and AWS services

## AWS CloudTrail
* Logs and tracks all API calls to AWS services
* Logs are kept for 90 days by default
* Managements events are logged by default
   * Operations performed on your AWS resources(CreateSubnet, AttachRolePolicy)
   *  Read Events and Write events
* Data Events are not logged by default
   * S3 object-level transactions as an example
* CloudTrail Insights - are used to detect unsual activity in your account
* To keep event longer than 90 days log them to S3 and use Athena

## AWS Config
* Records configurations and changes over time for auditing and compliance of your AWS resources
* Examples: Buckets public access? Public SSh access in my security groups
* AWS Config Rules do prevent actions from happening
* Can auto remediation of non-compliant resources by using SSM automation Documents


