# Compute

## EC2
* Virtual instance running in the cloud
* Instance types
  * General Purpose - Can handle a diverse workload
  * Compute Optimized - More CPU and process intensive tasks
  * Memory Optimized - Fast memory
  * Storage Optimize - High IO operations
  * GPU optiomized - AI, Deep learning, ML

# Elastic Network Interface
* Cannot remove primary ENI
* Can assign a public EIP that stays with the ENI
* Can detach and reattach from ec2 instance
* ENI must be in the same availability zone as the instance

# Elastic Beanstalk
* Handles deployment of AWS instructure for your application
* Developers uploads application code and Beanstalk does the rest
* Envrionments - dev, test, prod
* Easy deployment of full stack apps. Support all of the major runtimes.
* Autoscaling and managed platform updates

# ECS
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
