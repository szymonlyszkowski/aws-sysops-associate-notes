# Elastic Block Storage

1. Types of EBS:
   * General purpose SSD (gp2) - max __16TB__ & __10000 IOPS__
   * Provisioned IOPS (io1) - max __16TB__ & __20000 IOPS__
   * Throughput optimized HDD (st1)
   * Cold HDD (sc1)
   * Magnetic (standard)

1. EBS Monitoring
   * EBS automatically send metrics data to cloudwatch __ONLY__ when it is attached to EC2 !
   * __Provisioned IOPS__ - uses detailed monitoring in Cloudwatch (gather metrics every __1__ minutes)
   * Other types of EBS - uses standard monitoring in Cloudwatch (gather metrics every __5__ minutes)

1. Amazon Data Lifecycle Manager (Amazon DLM)
Can be used to __automate__: _creation, deletion, retention_ of snaphots taken from EBS volumes. Such automation helps to:
   * Protect valuable data by enforcing regular backup schedule
   * Retain backups required by __internal compliance__ & __auditors__
   * __Reduce storage costs__ by deleting outdated backups

1. EBS Limits:
   * Snapshot per region: __100,000__
   * Snapshot __concurent copy__ to another aws region limit: __20__ per account 
   * Snapshots enabled for fast snapshot restore	__50__
