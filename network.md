# Network

## VPC
* Virtual private datacenters that isolate AWS services within the same account
* Contains, subnets, route tables, firewalls, gateways
* Each VPC residse in one region
* Acts as a network boundary, cannot communicate between VPCs by default
* Each VPC is assigned an IP CIDR block between /16 and /28
* One default VPC per region (172.31.0.0/16)
* Custom VPCs are created by the administrator
* One /20(4096 addresses) default subnet in each availability zone
* Default VPC has the an Internet Gateway attached to the VPC
* Route 0.0.0.0/0 to IGW in all subnets
* 
