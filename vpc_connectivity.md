#### VPC connectivity options

1. VPC to VPC
  * __VPC peering__ _Recommended solution. CIDRs cannot overlap. Can be done between VPCs in same or different account. Supports routing between private IPs. Can be done in the same of different AWS regions(to verify)_
  ![](./vpc_vpc_peering_vpc.png)
  * __Hardware VPN__ _Recommended approach when you want to take advantage of AWS-managed VPN endpoints including the automated multidata center redundancy and failover built into the AWS side of each VPN connection. Although not shown, the Amazon VGW represents two distinct VPN endpoints, physically located in separate data centers to increase the availability of each VPN connection._
  ![](./vpc_hardware_vpn_vpc.png)
  * Software VPN
  * Software to Hardware VPN
  * AWS Direct Connect
2. VPC to datacenter
  * __Hardware VPN__
  _Consider taking this approach when you want to take advantage of an AWS-managed VPN endpoint that includes automated multi–data center redundancy and failover built into the AWS side of the VPN connection. Although not shown, the Amazon virtual private gateway (VGW) represents two distinct VPN endpoints, physically located in separate data centers to increase the availability of your VPN connection_.
  ![](./harware_vpn_vpc_dc.png)
  * __AWS Direct connect__
  _Dedicated network connection over private lines_
  ![](./vpc_aws_direct_connect_dc.png)
  * __AWS Direct connect + VPN__ _With AWS Direct Connect + VPN, you can combine one or more AWS Direct Connect dedicated network connections with the Amazon VPC hardware VPN. This combination provides an IPsec-encrypted private connection that also reduces network costs, increases bandwidth throughput, and provides a more consistent network experience than Internet-based VPN connections._
  ![](vpc_aws_direct_connect_&_vpn_dc.png)
  * __AWS Cloud Hub__ _Use when trying to connect multiple remote office branches. Reuse existing internet connections between branches_
  ![](./vpc_aws_vpn_cloud_hub_dc.png)
  * __Software VPN__ _This option is useful when you need to manage both side of connections due to compliance reasons or leveraging gateway devices not supported by AWS_
  ![](./vpc_software_vpn_dc.png)
3. VPN clients connecting to VPC
  * __Software Remote access VPN__ _Using existing VPN technologies to connect to AWS VPC(s)_
  ![](./vpc_client_vpn.png)
  * __User network to AWS VPC options__ _Virtual extension of existing VPN connection do User network__
