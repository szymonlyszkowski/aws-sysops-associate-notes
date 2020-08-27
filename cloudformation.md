### Cloudformation

* CF is free of charge. You pay only for provisioned resources using cloud formation
* Use AWS IAM to control access to CF resources & templates
* CF templates can be stored in git
* CloudFormation provides a set of application bootstrapping scripts that enable you to install packages to your AWS resources
* You can provision & update your infrastructure using a __template__
* __Templates__ are stored as `.yaml` or `.json` file
* A collection of associated resources within __template__ is called a __stack__
* __Stacks__ can be applied via AWS CLI, AWS API, AWS Console

CF:

* __resources__ - a list of resources to be created within stack (e.g. EC2) __MANDATORY__ !
* __conditions__ - specifies if given resources or their parameters are optional during creation or update (optional)
* __parameters__ - input values for stack (optional)
* __outputs__ - output values from stack (e.g url to created application, optional)
* __format version__ - template version (optional)
* __desciption__ - description for template (optional)
* __mappings__ -  mapping of keys and associated values that you can use to specify conditional parameter values, like a lookup table. (optional)
* __transform__ - for AWS lambda, specifies AWS Serverless Application Model (AWS SAM) to use (optional)
* __metadata__ - additional info about template
