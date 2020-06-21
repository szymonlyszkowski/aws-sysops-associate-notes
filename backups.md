###### Database backup approaches:
* Using EBS Snapshot when DB deployed in regular instance. Should be done in read replica (second instance)
* RDS backups:
   * Automated backup. Up to 35 days (uses transaction logs). `LatestRestorableTime` (usually 5 minutes). `DescribeDBInstances` to find latest restorable time.
   * DB Snapshot. Can be done at every frequency. Restore at every time you want. Use AWS Console or `CreateDBSnapshot` to restore DB. New endpoint will be created (possible to create multiple databases). Console or `DeleteDBSnapshot` to remove old backup(s). Console or `DeleteDBInstance` to remove old instances.
