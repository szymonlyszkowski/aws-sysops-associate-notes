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
* **TXT** - A TXT record contains one or more strings that are enclosed in double quotation marks (")
* **SRV** - consists of four space-separated values. The first three values are decimal numbers representing priority, weight, and port. Last one is domain name. Example:
```
10 5 80 test.example.com
```
* **ALIAS** - allows you to point to AWS specific resources e.g. cloudfront, S3. Allows as well to point from one record in hosted zone to another record.
* **CNAME** - A CNAME record can redirect DNS queries to any DNS record. For example, you can create a CNAME record that redirects queries from acme.example.com to zenith.example.com or to acme.example.org. You don't need to use Route 53 as the DNS service for the domain that you're redirecting queries to.

Unlike a CNAME record, you can create an alias record at the top node of a DNS namespace, also known as the **zone apex**. For example, if you register the *DNS name example.com*, the *zone apex is example.com.* You can't create a CNAME record for example.com, but you can create an alias record for example.com that routes traffic to www.example.com.
