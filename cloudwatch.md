# Cloudwatch
* Cloudwatch is metrics repository. With such repository you can get statistics.
* You can use metrics to calculate statistics and then present the data graphically in the CloudWatch console.
* Metrics are stored separately in Regions but you can use CloudWatch cross-Region functionality to aggregate statistics from different Region
* You can provide your own custom metrics to cloudwatch.

* Concepts in CW:
   - Namespaces
   - Metrics - fundametnal concept in CW. **Time-ordered set of data point** published to CW. Metrics exists only in region where they were created. Metrics **cannot be deleted** but they expire after **15** months if given **metric** is not updated.
   - Dimensions
   - Statistics
   - Percentiles
   - Alarms

**Billing alarms** - Before you can create an alarm for your estimated charges, you must enable billing alerts, so that you can monitor your estimated AWS charges and create an alarm using billing metric data. After you enable billing alerts, you cannot disable data collection, but you can delete any billing alarms that you created __(enable billing alarms in account preferences)__

[Custom foo description](#foo)



#### EC2 Default CW Metris:
* `CPUUtilization`
* `DiskReadOps`
* `DiskWriteOps`
* `DiskReadBytes`
* `DiskWriteBytes`
* `NetworkIn`
* `NetworkOut`
* `NetworkPacketsIn`
* `NetworkPacketsOut`
* `MetadataNoToken`

* __Instance Status Check__ - Verifies if VM is running correctly (issues of: incorrect networking/startup setup, memory overusage, incompatible kernel, corrupted filesystem) 
* __System Status Check__ - Verifies if Physical Host is running correctly (issues of: network connectivity, hardware or software, loss of system power)
* __RAM usage__ is a __custom__ metric!

There are two variants of EC2 instances monitoring: __detailed__ & __basic__. By default basic monitoring is enabled.
* __Basic monitoring__ - gathers data every __5__ minutes (63 days of retention)
* __Detailed monitoring__ - gathers date every __1__ minute (14 days of retention, even after EC2 instance is terminated)

### Cloudwatch Alarms
* You can create **alarms** based on statistics which initiate (when outside of threshold):
  - EC2 ASG
  - Amazon SNS
* __Metric alarm__ - watches single CW Metric or __result__ of math expression based on CW Metric. Alarm performs __one__ or __more actions__ based on the value of the metric or expression relative to a threshold over a number of time periods. Actions can be performed on services: __EC2, ASG, SNS__
* __Composite alarm__ - inludes the expression of that takes into account states of other alarm states. The composite alarm goes into ALARM state __only if all conditions of the rule__ are met!


TODO:
* When use CW + AWS SNS
* When use Cw + AWS SES

Cloudwatch - metrics with high resolution.

![](./cloudwatch_integrations.png)
