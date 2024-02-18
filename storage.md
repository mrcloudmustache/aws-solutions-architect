# Storage

## EBS
* Stores files in scalable block storage solutions that are attached to EC2 instances
* Capacity size limites between 1TB up to 64TB
* "E" stands for elastic. Can increase capacity or performance after creation.
* Can Multi-attach 1 EBS volume to up to 16 nitro backed EC2 instances
* Redundant within a single availabiliy zone across multiple devices

Volume commands
```
# list block devices
lsblk
# verify files system
sudo file -s /dev/xvdf
# create xfs file system
sudo mkfs -t xfs /dev/xvdf
# create mount directory
mkdir -p /home/ec2-user/ebsdemo
# mount volume 
sudo mount /dev/xvdf /home/ec2-user/ebsdemo
# unmount volume
sudo ummount -l /home/ec2-user/ebsdemo
```

## AWS Outposts
* Lets end users run AWS services on premises in their own datacenters

## S3
* Buckets of unlimited object cloud storage
* Type is object storage
* Any data type such as Cloudwatch logs, AMIs, EBS snapshots etc.
* Encrypted by default
* Storage classes
  * Standard
    * Instant low latency retrieval
    * Files can be made publically available
  * Standard IA
    * Enforces a retrieval fee
    * Will be charged a fee for a minimum duration of 30 days.
  * S3 One Zone IA
    * Stored in one availabity zone
  * S3 Glacier-Instant
    * Low cost option for rarely accessed data.
    * Access to data immediately
    * Will be charged a fee for a minimum duration of 90 days.
  * S3 Glacier-Flexible
    * Data is a sleep until you wake up 
    * Retrival options are Bulk, Expedited, Standard.
    * Data is temporarily stored in Standard IA during retrival.
  * S3 Glacier Deep Archive
    * cheapest s3 class
    *   Will be charged a fee for a minimum duration of 180 days.
    *   Retrival options are Bulk, Standard.
  * S3 Intelligent-Tiering
    * Automates moving data to lower cost storage options.
* Versioning is enabled on the bucket not the individual file.
* Can only suspend versioning. Current versions stay in place.
* IAM policy
  * Can only be applied to authenticated AWS users
  * Cannot be applied to anonymous users
* Resource Policy
  * Can be applied to anonymous/public users
* AWS does not recommend using S3 ACLs

Bucket policy example
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowAll",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": [
                "arn:aws:s3:::mrcloudmustache/*",
                "arn:aws:s3:::mrcloudmustache"
            ]
        }
    ]
}
```

## S3 Glacier
* Provides archive storage for cold data thats accessed infrequently
* Object storage
* Managed through GET, PUT API calls
* Entire object is updated with any modifications
* Encrypted by default

## EFS
* Provides a shared file system for Linux and Windows systems
* Up to Petabytes of storage capacity

## EFS (FSx)
* Provides a shared file system for Windows systems
* SMB Protocol





