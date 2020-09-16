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


##### Route 53 Healthchecks
1. Determine healthcheck which monitors an __endpoint__
    * Based on response time (network can be down, DDoS can be present)
    * Based on healthcheck status (if 18% of __health checkers__ or more is healthy consider healthy if not unhealthy)
        * __HTTP/S__ checkers - consider connection established within __4__ seconds as healthy + response with __2XX & 3XX__ status code __after__ connection is established
        * __TCP__ checker - consider connections established within __10__ seconds as healthy
        * __HTTP/S with string check__ - TODO
      
1. Determine healthcheck which monitors __other healthchecks__
   * TODO
   
1. Determine healtcheck based on __Cloudwatch alarm__
   * When alaram in __OK__ state - healthcheck __healthy__
   * When alarm in __ALARAM__ state - healtcheck __unhealthy__
   * When alarm __INSUFFICIENT DATA__ - healthcheck status dependent on setting _Health check status_: healthy, unhealthy, or last known status. In route53 API this setting is `InsufficientDataHealthStatus`.   
   > When setting up __new__ healthcheck - __by default__ healthy when not enough data to determine actual state. This behaviour can be changed using __invert the health check status__
