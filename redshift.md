### AWS Redshift

Amazon Redshift is a **fully managed**, petabyte-scale data warehouse service in the cloud. You can start with just a few hundred gigabytes of data and scale to a petabyte or more.

With Redshift cluster (consists of a leader node and one or more compute nodes), you can upload your data set and then **perform data analysis queries**. Regardless of the size of the data set, Amazon Redshift offers **fast query performance** using the same SQL-based tools and business intelligence applications that you use today.

* It is possible to add or remove nodes without cluster disruptions.
* Cluster cost savings - if you intend to keep your cluster running **for a year or longer**, you can save money by **reserving compute nodes** for a one-year or three-year period.

* Manual or Automatic snapshots supported. Snapshots stored in S3, transferred over secure SSL connection. If restore needed Redshift **creates new cluster** and imports data from snapshot.

* Encryption supported (can be done via AWS KMS).
  * **Immutable** property of the cluster.
  * **Only way** to move from encrypted to unencrypted cluster is to unload data from old one and put into new one.
  * Encryption applies to cluster and snapshots.
  * When snapshots are encrypted restored cluster is encrypted as well.
  * SSL Connections to Redshift cluster are supported


* **Paramter groups** - define the behavior of all databases in a cluster, such as date presentation style and floating-point precision. If you don’t specify a parameter group when you provision your cluster, Amazon Redshift associates a default parameter group with the cluster

* By default cluster creates **ONE** database. It is possible to create **more** databases by running SQL command.

* Audit logging:
  * authentication attempts
  * connections
  * disconnections
  * changes to database user definitions
  * queries run in the database

* Performance metrics (stored in cloudwatch):
  * CPU Utilization
  * Latency
  * Thoughtput

* Events & Notifications (uses AWS SNS):
  * Notifications sent by subscription to specified event or set of events.
  * date the event occurred
  * event description
  * event source (for example, a cluster, a parameter group, or a snapshot), and the source ID.
