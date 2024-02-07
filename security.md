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
* Records all API actions against AWS services, who, what, when
* Stores 90 days by default, store in S3 or CloudWatch log group for anything longer
* Good for auditing, compliance and incident response
* Can send logs to S3 or Cloudwatch
* Is a regional service and logs must be viewed seperately in each region
* Tracks both data and management events

## Config
* Tracks configuration changes across AWS resources, historical view of changes over time.
* Can notify changes to your resources
* Keeps inventory of AWS resources, data stored in S3 bucks and DynamoDB.
* Can set desired configurationn state for a resource and get notified of any devition from this state.
* Can track relationships between resources. This helps with understanding the impact of changes.

## Artifact
* AWS compliance reports
* Centralized audit repository in the management console
* Free of charge

## Guard Duty
* Analyzes logs for malicious or unusual activity
* Cloudtrail logs, vpc flow logs, DNS logs
* Can trigger lambda functions
* Can provide a trusted IP list and a threat IP list(vpc flow logs)
* Supports AWS organizations
* Useful for large workloads where inspecting each device by hand is not possible
* Maleware protection creates replica snapshots of affected EBS volumes.
* Integrates with Security hub

## Inspector
* Scan aws systems for vulnerabilties
* EC2, ECS, Lambda
* Continuous monitoring
* Create different environments with different scanning settings(asessment target)
* Tag the EC2 to define the assessment target
* Package, Code vulnerabilites and network rechability by assessing wide open security groups for example

## Macie
* Uses ML to find sensitive data in S3 buckets
* Used for PII
* Prevents data leaks
* Sensitive data can be identified using custom identifiers or keywords you configure
* Can publish findings to EventBridge
* Can analyze encrypted objects except those encrypted with Customer provided keys.
* Real time logging to CloudWatch
* Can setup one time or jobs to run on a schedule

## Security Hub
* Central location for all security data
* Central view
* Prioritize most critical events
* Can automate remidiation
* Compliance checks


## KMS
* Used for encryption
* Used to manage encryption keys
* Creation, rotation and deletions of keys
* Encrypt files
* Integrations - S3 key is KMS, Encrypted EBS, RDS etc.
* Customer master keys - primary resource 4KB only
* Data keys - used to encrypt large amounts data larger than 4KB
* Imported key material
* AWS managed keys - S3, EBS AWS controlled
* AWS Owned keys - not visible in the account
* Symmetric keys - uses one key for encryption and decryption
* Asymmetric keys - private public key
* Encrypt data with data key > encrypt plain text data key with CMK

## CloudHSM
* All encryption keys are stored on one server
* Managed HSM module in the cloud
* Can deploy in a HA cluster
* Full control over your keys

## Certificate Manager
* Generate SSL/TLS certifcates for securing connections to web services
* Supports - ELB, CloudFront, API Gateway
* Not supported - EC2, S3 and Amazon Lambda
* Certificates are region dependent

## Private Certificate Authority
* Scalable service that manages private certificates for internal systems
* Can integrate with ACM for automated renewals

## Secrets Manager
* Stores, rotates and manages organizationalsecrets
* Can store credentials for APIs, SSH keys, databases etc
* Secrets are encrypted at rest with CMKs or AWS KMS(default)
* Applications in a VPC can use a private interface to connect directly to AWS secrets manager

## AWS Trusted Advisor
* A managed service that checks runs essential checks against your AWS account
* Security checks, open S3 buckets, public RDS snapshots, root accounts without MFA enabled
* Checks service quota limits
* With Business support advisor can check for unassigned Elastic IPs




