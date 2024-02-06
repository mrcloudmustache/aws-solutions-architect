# Security Services

## IAM

## Congnito

* Provides authentication service for custom applications.
* Developers do not have to roll their own auth and can focus on business objectives instead.
* Receives a token and provides it to the application.

## Directory Service

Simple AD
* Cannot integrate with other AD systems.
* Limited feature set.
* Uses SAMBA

Managed Microsoft Active Directory
* Can create a trust relationship to on-premises AD
* AD connectory mode creates an AD proxy instead of another instance of AD

## Verified Permissions
* A scalable service for managing permissions(authorization) in custom apps
* Charged by authorized requests
* Responds with yes or no is the the user authorized
* Users are authenticated using other service such as OpenID connect or AWS Cognito.

Benefits
  * Seperates business logic form authorization logic
  * Zero trust
  * All requests are verified through service

## CloudTrail

* Tracks all API actions against AWS services, who, what, when
* Stores 90 days be default, store in S3 for anthing longer
* Good for auditing, compliance and incident response
* Can send logs to S3 or Cloudwatch

## Config

* Tracks configuration changes across AWS resources
* Can notify changes to your resources
* Keeps inventory of AWS resources
* Can set desired configurationn state for a resource and get notified of any devition from this state.
* Can track relationships between resources. This helps with understanding the impact of changes.


