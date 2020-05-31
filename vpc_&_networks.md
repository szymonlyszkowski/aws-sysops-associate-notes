#### VPC 
* VPC limit per region is **5**. Can be increased on demand.
* Internet gateway is the same as VPC limit.
* Subnets limit per VPC is **200**
* Subnet is created per **one** availability zone (AZ)
* It is possible to increase the size of VPC by using `secondary/additional CIDR blocks/ranges` when using IPv4. Shirking is possible by removing secondary ranges. It's not possible to shrink, increase basic CIDR blok. **Resize** not possible for IPv6.
