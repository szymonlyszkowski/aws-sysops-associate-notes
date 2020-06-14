#### Elasticache:
* Redis - supports advanced data structures: **sorted sets, hashes,listsorted sets, lists**
* Redis usage typical architecutre: EC2s in ASG, Redis node & Redis replica, RDS
* Redis can have up to 5 Read Replicas

* Memcached typical architecture: EC2s in ASG, Memcached Cluster, RDS/DynamoDB

### Memcache metrics:
* `CPUUtilization` - Because Memcached is multi-threaded, this metric can be as high as 90%. If you exceed this threshold, scale your cache cluster up by using a **larger cache node type**, or scale out by **adding more cache nodes**.
* `SwapUsage` - This metric should not exceed 50 MB. If it does, we recommend that you increase the `ConnectionOverhead` parameter value.
* `Evictions` - If you exceed your chosen threshold, scale your cluster up by using a **larger node type**, or scale out by **adding more nodes**.
* `CurrConnections` - An increasing number of CurrConnections might indicate a **problem with your application**, you will need to investigate the application behavior to address this issue.


