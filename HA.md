
###### Achieving HA
 * Use ELB (users connect via DNS name). ELB points to instances in multiple AZs & verify via health checks
 * Use Elastic IP - If the instance fails, **reassociate** the Elastic IP address to a different instance, which will then start receiving the traffic immediately.**This method is not recommended** because only one instance is receiving all the traffic while the other instance(s) are sitting idle. It also requires a mechanism to detect failure and reassociate the Elastic IP (which you must do yourself).
 * Use ENI - all EC2s have ENIs. They can have **additional** ENIs.
 It is possible to direct traffic to a secondary ENI and then move that secondary ENI to another instance. This is similar to reassigning an Elastic IP address. **ENIs can be reassociated within single AZ!**

Long story short - ELB where possible to achieve HA.
