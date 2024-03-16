# Database

## RDS
* Relational database
* Instance types
  * General purpose - all-around performance random read and write
  * Memory optimized - large data sets require lots of in memoryMulti
* Single RDS - one AZ
  * staging and development environments
  * lower cost
* Multi-AZ
  * Replicate data to standby into a different AZ
  * Synchronous replication
  * DNS name redirected to standby DB when a failure is detected
  * Can promote standby to primary DB for writes
  * More expensive
  * No reads and writes on the standby DB
  * Read replicas can be setup with multi AZ
  * Zero downtime when enabling multi AZ
* Read replica
  *  Asyncronous replication(eventually consistent)
  *  Distributes read traffic between multiple databases
  *  Reduces load on your primary database
  *  Can promote to a standalone instance if primary DB fails
  *  Can create cross-region read replicas to reduce latency from global users
  *  Applications must use the reader endpoint
  *  No fee for cross AZ replication when primary DB is in the same region.
* Auto-scaling - automatically scales store when space is low. Can set maximum storage limit.
* Storage types
  * General Purpose SSD - use for a broad range of workloads, dev and test environments, 3000 iOps
  * Provisioned IOPs SSD - designed for I/O intennsive workloads, low I/O latency, consistent I/O througput, production environments, Max 16TB
  * Magnetic - Hard disk drives, not supported by some DB engines
* RPO of 5 minutes
* RDS events only provide operational events such as DB instance events, DB parameter group events, DB security group events, and DB snapshot even

## RDS Custom
* Full access to EC2 instance
* Use with Oracle and MS SQL

## Aurora and Aurora Serverless
* Supports MySQL and PostgreSQL DB engines
* Decouples compute and Data storage. Can scale each independently.
* 20 percent higher cost than RDS
* Continuous backup to S3 with 1 up to second RPO for the past 35 days
* Six copies of data two in each AZ, across 6 storage nodes.
* Automatically grows between 10GB up to 128 TB of storage
* Requires 4 of 5 nodes for writes
* Requires 3 of 6 nodes for reads
* Can lose one AZ and still be operational
* Writer endpoint points to master DB
* Reader endpoint connection load balancing between all read replicas
* Aurora types
  * Provisioned
    * Fixed capacity
    * Have to manually scale up and down
    * Supports Aurora global regions
  * Serverless
    * Autoscaling
    * Best for dynamic workloads
    * Aurora global V2 only
* Aurora capacity unit(ACU)
  * One ACU 2 GB of memory, CPU, and networking
  * Provide min(0.5) and max(128) ACUs

## RDS Proxy
* Establishes a fixed number of DB connections, then the application opens connections to RDS Proxy instead of directly to the database.
* Allowing the proxy to queue or throttle connections
* Improves DB performance
* RDP proxy re-routes traffic after a DB failover which increases availability
* Can enforce IAM and secret manager
* Fully managed

## DynamoDB
* Fully managed scalable NoSQL database
* Tables - a collection of data. Users or products table.
* Items - entry with the table. Each user is an item.
* Attributes - properties of an item within the table.
* Primary key - uniquely identifies each item in the table
  * Single attribute - Partition Key
  * Composite - Partition and Sort key. Both attributes make up the primary key
* Tables are schemaless
* Table classes
  * Standard Access - default option with full performance of DynamoDB
  * Standard Infrequent Access - useful for logs not accessed very often. application logs, order history, old social media posts
* Supports Key value and Document data
* Zero downtime maintenance
* Global tables active-active which means you can read and write the DB in each region
 * Requires enabling DynamoDB streams for replication
* Secondary indexes - allows sorting and query on non-primary keys, enhancing query performance and efficiency
* DynamoDB stream - sends CRUD events to other integrations
* Use cases - Real-time applications, media metadata stores, scales to support millions of connections
* DynomaDB Accelerator(DAX) - in-memory caching service for DynamoDB
  * Microsend latency for cached data
  * Does not require application logic changes
  * Cache none - one primary others are read replicas
* DynamoDB Streams
 *  Stream of ordered item level changes in a table
 *  Limited consumers
  * DynamoDB KCL adapter
  * Lambda  
 *  24 hour retention
* Kinesis data streams
 * 1 year of retention
 * High consumers
  * AWS Glue, Kinesis data firehouse

## Redshift
* Datawarehouse that is designed to start large amounts of data from different sources
* Unified view of your data
* Columnar storage of data and parallel query engine
* Optimized for complex analytics queries (OLAP)
* Has a SQL interface
* Must load data into Redshift vs ad hoc query versus Athena
* Leader node - Manage client connections generate queries and send them to the compute nodes
* Compute nodes - Store data records and execute all the queries from the leader node. All are performed in parallel.
* Redshift spectrum - Can run queries against S3 without loading the data into the Redshift cluster.

## ElastiCache
* Managed In-memory caching service
* Minimizing latency because requests do not have to go to the database
* Sits in front of DB so frequent reads are requested from the cache
* Global Datastore
* ElastiCache fot Redis
  * Supports read replicas
  * Data is persistent
  * Supports encryption at rest
  * Support pub/sub message system
* ElastiCache for Memcached
  * Supports multi-AZ deployments
  * No data persistence
  * Useful for storing users session state
  * Auto discovery automatically adds or removes nodes based on performance
  * Supports sharding which distributes your data across multiple nodes

