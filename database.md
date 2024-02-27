# Database

## RDS
* Relational database
* Instance types
  * General purpose - all around performance random read and write
  * Memory optimized - large data sets require lots of in memoryMulti
* Single RDS - one AZ
  * staging and development evironments
  * lower cost
* Multi-AZ
  * Replicate data to standby into a different AZ
  * Can promote standby to primary DB for writes
  * More expensive
* Read replica
 *  Distributes read traffic between multiple databases
 *  Reduces load on your primary database
 *  Can promote to a standalone instace if primary DB fails
 *  Can create cross-region read replicas to reduce latency from global users
* Storage types
 * General Purpose SSD - use for broad range of workloads, dev and test environments, 3000 iops
 * Provisioned IOPs SSD - designed for I/O intennsive workloads, low I/O latency, consistent I/O througput, production environments, Max 16TB
 * Magenetic - Hard disk drives, not supported by some DB engines
* RPO of 5 minutes

## Aurora and Aurora Serverless
* Supports mySQL and PostgreSQL DB engines
* Decouples Compute and Data storage. Can scale each independently.
* Continuous backup to S3 with 1 up to seconcd RPO for past 35 days
* Six copies of data two in each AZ, across 6 storage nodes.
* Up to 128 TB of storage
* Requires 4 of 5 nodes for writes
* Requires 3 of 6 no for reads
* Can lose one AZ and still be operational
* Aurora types
 * Provisioned
  * Fixed capacity
  * Have to manually scale up and down
  * Supports Aurora global regions
 * Serverless
  * Auto scaling
  * Best for dynamic workloads
  * Auora global V2 only
  * Aurora capacity unit(ACU)
   * One ACU 2 GB of memory, CPU, and networking
   * Provide min(0.5) and max(128) ACUs

## RDS Proxy
* Establishes a fixed number of DB connections, then application open connections to RDS Proxy instead of directly to the database.
* Allowing the proxy to queue or throttle connections
* Improves DB performance
* RDP proxy re-routes traffic after a DB failover which increases availability
* Can enforce IAM and secret manager
* Fully managed
