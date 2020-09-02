# Elastic Block Storage

1. Types of EBS:
  * General purpose SSD (gp2)
  * Provisioned IOPS (io1)
  * Throughput optimized HDD (st1)
  * Cold HDD (sc1)
  * Magnetic (standard)

2. EBS Monitoring
  * EBS automatically send metrics data to cloudwatch __ONLY__ when it is attached to EC2 !
  * __Provisioned IOPS__ - uses detailed monitoring in Cloudwatch (gather metrics every __1__ minutes)
  * Other types of EBS - uses standard monitoring in Cloudwatch (gather metrics every __5__ minutes)
 
