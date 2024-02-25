# Compute

## EC2
* Virtual instance running in the cloud
* Instance types
  * General Purpose - Can handle a diverse workload
  * Compute Optimized - More CPU and process intensive tasks
  * Memory Optimized - Fast memory
  * Storage Optimize - High IO operations
  * GPU optiomized - AI, Deep learning, ML

## Elastic Network Interface
* Cannot remove primary ENI
* Can assign a public EIP that stays with the ENI
* Can detach and reattach from ec2 instance
* ENI must be in the same availability zone as the instance

## Elastic Beanstalk
* Handles deployment of AWS instructure for your application
* Developers uploads application code and Beanstalk does the rest
* Envrionments - dev, test, prod
* Easy deployment of full stack apps. Support all of the major runtimes.
* Autoscaling and managed platform updates

## ECS
* Containers allow you to package all of the application files and dependencies needed for the application to run
* Lightweight version of virtual machines
* Acts as a continer orchestrator. Like K8s.
* Two options for container runtimes, EC2 or Fargate(serverless)
 * EC2 launch type - you to manages the EC2 instances
 * Fargate - AWS managed the underlying infrastructure
 * ECS task definition - provides images and container configurations
  * CPU, memory
  * Image, ports, volumes
  * Like Docker compose
* A task is a running container
* A service?
* Load balancer

## EKS
* A managed kubernetes service
* Creates master nodes for you
* Handles scaling and backups
* User is responsible for the worker nodes
 * Slef managed nodes - admin manually provisions ec2 instances,
 * Managed node group - automated provisioning of ec2 nodes EKS optimized images, node is part of autoscaling group managed by EKS
 * Fargate - Will create worker nodes on demand. Fully managed by AWS.

## ECR
* AWS managed contianer registry used for centrally hosting container images
* Public ECR - accessible from internet, need to be authenticated to push images
* Private ECR - not accessible from intenet, need to be authenticated to pull and push images
* Cannot change visibility after repository is created
* Image lifecycle management
* Security image scanning

## CloudWatch
* Monitors AWS resources metrics in real-time
* Can trigger alarms and use SNS to send notifications
* Can store and collect logs
* Publish custom metrics to namespaces
* EventBridge???

## CloudTrail
* API activity is logged to a CloudTrail Event
* Logs management events by default. Data events are optional.
* 90 days of logs are kept by default
* Most trails are logged to the regions where the service reside
* Global service events are logged to us-easat-1 such as IAM, STS, Cloudfront
* Custom trails can be stored in S3 or CloudWatch logs
* Organization trails are enabled in the management account and logs acticity from all accounts
* Not realtime - 15 minutes within activity timestamp

## EC2 Autoscaling
* Scales EC2 in or out based on scaling polices.
* Scaling policies
  * Manual - min, desired, max - will always have number of desired instances
  * Dynamic
    * Target tracking - tracks target metrics such as networkIn, CPU, etc
    * Simple scaling - cloudwatch alarms control scaling, can specify n number of instances to add or remove. Fixed scale value
    * Step scaling - same as simple, with extra features. Can trigger at multiple levels. Between 10-20 add 1 instance, between 20-30 add 5 instances.
  * Scheduled - scales at scheduled times
  * Launch template - defines specs for the EC2 instances added to scaling group
    * Instance config - access key, instance type, ami id, network configuration
    * Versioning for easy updates
    * Customizations using parameters
   * Integrations - ELB, CloudWatch, EC2, SNS

## Lambda
* Serverless service that executes functions bases on triggers
