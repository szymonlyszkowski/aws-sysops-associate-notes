### Read replicas

* Read replicas can be promoted to standalone DB instances.
* Read replicas available for: *MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Amazon Aurora*
* *Amazon Aurora* uses virtualized SSD-backed storage layer. Aurora replicas share the same underlying storage as the source instance, lowering costs and avoiding the need to copy data to the replica nodes.
* **Multi-AZ**: High Availability
* **Read replica**: Read scalability
* **Aurora Global Database** to replicate data from multi-az to another region
* Create a read replica by specifying `SourceDBInstanceIdentifier`, which is the DB instance identifier of the source DB instance that you want to replicate from.
* Within an AWS Region, all read replicas must be created in the same virtual private cloud (VPC) based on Amazon VPC as the source DB instance. This requirement applies even if VPC peering is configured in the AWS Region.
* For cross-Region read replicas, any of the create read replica commands that specify the `--db-subnet-group-name` parameter must specify a DB subnet group from the same VPC.
* Read replica promotion to *Standalone*. The promotion process takes a few minutes to complete. When you promote a read replica, **replication is stopped and the read replica is rebooted**. When the reboot is complete, the read replica is available as a new DB instance.

Example of creating cross-region read replica:
```
aws rds create-db-instance-read-replica \
    --db-instance-identifier SimCoProd01Replica01 \
    --region us-west-2
    --source-db-instance-identifier arn:aws:rds:us-east-1:123456789012:db:SimcoProd01 
```

###### Security RDS
* Using PKI it is possible to encrypt data during transit between read replicas (even between regions)
* Using AWS KMS it is possible to encrypt data in RDS at rest.
* Security group entries used to establish secure communication with RDS.


**Multi-AZ Deployment** | **Multi Region Deployment** | **Read replica**
:-------------------:|:-------------------|--------------------:
Main purpose is HA | Main purpose is DR and local performance | Main purpose is scalability
Non-aurora: Synchronous replication <br> Aurora: Asynchronous replication |  Asynchronous replication |  Asynchronous replication
Non-aurora: **Primary** instance is active <br> Aurora: **all** instances are active  |All regions are available for reads |All read replicas are availble for readscaling |
Non-aurora: Automated Backups taken from **standby** <br> Aurora: Automated Backups taken from **shared storage** | Automated backups can be done in each region|No Automated backups by default|
Always span at least to 2 AZ|Each region can have multi-AZ Deployment|Can be within AZ, cross-zone(az), cross-region|
Non-aurora: db version upgrades happen on primary<br> Aurora: all instances upgraded together |Non-aurora: db version upgrades happen independent on region <br> Aurora: db version upgrades happen at **all** regions|Aurora: db version upgrade is independent from source instance <br> Non-aurora: **All** instances upgraded together|
Non-aurora: automatic failover to standby <br> Aurora: automatic failover to read replica|Aurora: allows promotion to secondary region| Non-aurora: can be manually promoted to **standalone** instace <br> Aurora: Can be promoted to primary instance|
