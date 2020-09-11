#### VPC 
* VPC limit per region is **5**. Can be increased on demand.
* Internet gateway is the same as VPC limit.
* Subnets limit per VPC is **200**
* Subnet is created per **one** availability zone (AZ)
* It is possible to increase the size of VPC by using `secondary/additional CIDR blocks/ranges` when using IPv4. Shirking is possible by removing secondary ranges. It's not possible to shrink, increase basic CIDR blok. **Resize** not possible for IPv6.

##### NAT Gateway vs Egress-only internet gateway
* Egress-only igw - horizontally scaled, redundant, HA VPC component, prevents the internet from initiating an IPv6 connection with your instances.
* NAT Gateway - HA, managed service. Enables instances in a private subnet to connect to the internet or other AWS services, prevents the internet from initiating a connection with those instances.
* NAT Gateway supports IPv4 __only__.
* Egress-only igw supports IPv6 __only__.


###### NACL
* Rules are evaluated starting with the lowest **numbered rule**. As soon as a rule matches traffic, it's applied regardless of any higher-numbered rule that might contradict it.
