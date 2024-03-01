# Network

## VPC
* Virtual private data centers that isolate AWS services within the same account
* Contains, subnets, route tables, firewalls, gateways
* Each VPC residse in one region
* Acts as a network boundary, cannot communicate between VPCs by default
* Each VPC is assigned an IP CIDR block between /16 and /28
* One default VPC per region (172.31.0.0/16)
* Custom VPCs are created by the administrator
* One /20(4096 addresses) default subnet in each availability zone
* Default VPC has an Internet Gateway attached to the VPC
* Route 0.0.0.0/0 to IGW in all subnets

## Subnets
* Groups of IP addresses in the VPC
* Subnets reside in an availability zone
* Subnets can be private or public 
* Subnets must be within the CIDR range
* Subnet size must be between a /16 and /28
* The first 4 IP addresses are reserved
  * .1 VPC router
  * .2 DNS
  * .3 future use

## Route Tables
* Longer prefixes are preferred
* The VPC router routes traffic between subnets, and traffic in and out of the VPC
* Local route matches all routes local to the VPC, All RTs have 1 local for each address family IPv4/IPv6
* A subnet can only be associated with one route table

## Internet Gateway
* Enable resources to access the internet
* IGWs attach to a VPC in a specific region
* VPCs can only have one IGW attached
* Subnet is public once a route points towards the IGW

## NAT Gateway
* Allows traffic sourced from private subnets to the internet, but does allow traffic sourced from the Internet to instances on the private subnet
* Deployed to a subnet, so they are AZ resiliant and more than one should be create for fault tolerance
* Must be placed on a public subnet with a default route to the Internet Gateway
* Cost per hour per NAT instance

 
