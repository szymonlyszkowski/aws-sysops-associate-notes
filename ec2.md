###### EC2
API Calls:
`RunInstances` - start instances (max 20 by default)
**Complete the Amazon EC2 limit increase request form** - region based!
`DescribeInstances` - status of instances
`TerminateInstances` - terminate instances

* Instance metadata - data about your instance that you can use to configure or manage the running instance. Instance metadata has access to *user data*. 

*For example, you can specify parameters for configuring your instance, or include a simple script. You can build generic AMIs and use user data to modify the configuration files supplied at launch time.*

* Dynamic data - generated when the instance is launched (e.g instance identity document).

Local instance store vs. EBS for root device.
* EBS - By using Amazon EBS, data on the root device will persist independently from the lifetime of the instance(start/stop). When instance terimantes EBS is deleted. It can be set flag: `Delete On Terminate` to **NOT** remove EBS when terminating instance.
* Local instance store - only persists during the life of the instance(start/stop)

* It is **supported** to attach **multiple** volumes to instance
* It is **NOT supported** to attach **multiple** instances to one volume

##### performance-sensitive workloads: 
Any performance-sensitive workloads that require minimal variability and dedicated Amazon EC2 to Amazon EBS traffic, such as production databases or business applications, should use volumes that are attached to an EBS-optimized instance or an instance with 10 Gigabit network connectivity. EC2 instances that do not meet this criterion offer no guarantee of network resources. The only way to ensure sustained reliable network bandwidth between your EC2 instance and your EBS volumes is to launch the EC2 instance as **EBS-optimized or choose an instance type with 10 Gigabit network connectivity**


###### Create AMI
```
aws ec2 create-image
```
###### Create EBS Snapshot
```
aws ec2 create-snapshot
```
How to restore volume? (create volume from snapshot, detach old volume, attach new one)
```
1. aws ec2 create-volume –-region us-west-1b –-snapshotid mysnapshot-id
2. aws ec2 detach-volume --volume-id oldvolume-id –
instance-id myec2instance-id
3.  aws ec2 attach-volume --volume-id newvolume-id
--instance-id myec2instance-id --device /dev/sdf
```
*  Snapshots & AMIs can be shared across regions. Stored in S3
* `Private Snapshots` - snapshots shared with me
* `Public Snapshots` - snapshots shared globally

