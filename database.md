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
* 
