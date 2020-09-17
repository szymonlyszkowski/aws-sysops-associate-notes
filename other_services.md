# Other AWS services popular in exam questions


1. AWS SWF (Simple Workflow Service) -  scale background jobs that have parallel or sequential steps. You can think of Amazon SWF as a fully-managed state tracker and task coordinator in the Cloud.
1. Amazon Athena - interactive query service that makes it easy to analyze data in __Amazon S3 using standard SQL__.
   * Serverless,
   * Pay only for the queries that you run.
   * `LOCATION` format: __`s3://prefix/path`__ [docs](https://docs.aws.amazon.com/athena/latest/ug/tables-location-format.html)
1. Amazon QuickSight - fast, cloud-powered business intelligence service that makes it easy to deliver insights to everyone in your organization
   * Fully managed service
   * Pay-per-Session pricing
1. AWS Snowflake - makes modern data warehousing effective, affordable, and accessible to all data users within the organization. Snowflake enables the data-driven enterprise with instant elasticity, secure data sharing, and per-second pricing. Its built-for-the-cloud architecture combines the power of data warehousing, the flexibility of big data platforms, and the elasticity of the cloud.
1. AWS Snowball - transfare petabyte-scale data using device from your datacenter to AWS. __50-80 TB__ depending in AWS Region.
1. AWS Snowball Edge - is a type of Snowball device with __on-board storage and compute power for select AWS capabilities__. Snowball Edge can undertake local processing and edge-computing workloads in addition to transferring data between your local environment and the AWS Cloud. __100 TB__ in every aws region.
1. AWS Snowmobile - AWS Snowmobile is the first exabyte-scale data migration service that allows you to move very large datasets from on-premises to AWS. Each Snowmobile is a secured data truck with __up to 100PB__ storage capacity that can be dispatched to your site and connected directly to your network backbone to perform high-speed data migration. You can quickly migrate an exabyte of data with ten Snowmobiles in parallel from a single location or multiple data centers. Snowmobile is offered by AWS as a managed service.
