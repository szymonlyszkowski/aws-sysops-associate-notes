### Read replicas

* Read replicas can be promoted to standalone DB instances.
* Read replicas available for: *MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Amazon Aurora*
* *Amazon Aurora* uses virtualized SSD-backed storage layer. Aurora replicas share the same underlying storage as the source instance, lowering costs and avoiding the need to copy data to the replica nodes.
* **Multi-AZ**: High Availability
* **Read replica**: Read scalability
* **Aurora Global Database** to replicate data from multi-az to another region

###### RDS security
* Using PKI it is possible to encrypt data during transit between read replicas (even between regions)
* Using AWS KMS it is possible to encrypt data in RDS at rest.
* Security group entries used to establish secure communication with RDS.


**Multi-AZ Deployment** | **Multi Region Deployment** | **Read replica**
:-------------------:|:-------------------|--------------------:
  Main purpose is HA | Main purpose is DR and local performance | Main purpose is scalability
      Non-aurora: Synchronous replication <br> Aurora: Asynchronous replication     |  Asynchronous replication                |  Asynchronous replication
    Non-aurora: **Primary** instance is active <br> Aurora: **all** instances are active  |All regions are available for reads |All read replicas are availble for readscaling |
    Non-aurora: Automated Backups taken from **standby** <br> Aurora: Automated Backups taken from **shared storage** | Automated backups can be done in each region|No Automated backups by default|
    Always span at least to 2 AZ|Each region can have multi-AZ Deployment|Can be within AZ, cross-zone(az), cross-region|
    Non-aurora: db version upgrades happen on primary<br> Aurora: all instances upgraded together |Non-aurora: db version upgrades happen independent on region <br> Aurora: db version upgrades happen at **all** regions|Aurora: db version upgrade is independent from source instance <br> Non-aurora: **All** instances upgraded together|
    Non-aurora: automatic failover to standby <br> Aurora: automatic failover to read replica|Aurora: allows promotion to secondary region| Non-aurora: can be manually promoted to **standalone** instace <br> Aurora: Can be promoted to primary instance|
