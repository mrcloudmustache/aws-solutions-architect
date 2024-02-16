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
* Any data type such as Cloudwatch logs, AMIs, EBS snapshots etc.
* Encrypted by default

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





