#### Route 53

* Private hosted zone - used to resolve DNS names within associated VPCs
  - To use PHZ VPC must have following properties set to _true_:
    - `enableDnsHostnames`
    - `enableDnsSupport`
* Public hosted zone - contain records that specify how you want to route traffic on the internet.
* **NO** charge for the records that you add to a hosted zone

Record set types:
* **A** - IPv4 Address
* **AAAA** - IPv6 Address
* **MX** - mail exchange
* **CNAME** - canonical name
* **TXT** - 
