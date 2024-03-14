# Containers

## Docker
* Contiainerized application that can run on multiple operating systems
* Store containers in Docker hub or Amazon ECR 

## Amazon ECS
* EC2 launch type
  * You have to maintain the EC2 instances
  * EC2 runs the EC2 agent
* Fargate launch type
  * Serverless means no Ec2 instances to manage
  * You create task instances
  * Scale by increasing the number of tasks
* Load Balancers
  * ALB - used for most cases
  * NLB - used for high throughput and to pair with AWS Private Link
* Data Volumes
  * Mount EFS to the ECS task

## Amazon EKS
* Managed open source container management service
* Use case is the user is already running an instance of K8s and wants to migrate to AWS
* Supports EC2 and Fargate node deployments

## App Runner
* Managed service that deploys code without needing to configure any infrastructure
* Use source code or container
* Good for web apps, APIs and microservices
