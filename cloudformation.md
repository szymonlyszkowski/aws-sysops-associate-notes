### Cloudformation

* CF is free of charge. You pay only for provisioned resources using cloud formation
* You can provision & update your infrastructure using a __template__
* __Templates__ are stored as `.yaml` or `.json` file
* A collection of associated resources within __template__ is called a __stack__
* __Stacks__ can be applied via AWS CLI, AWS API, AWS Console

CF:

* __resources__ - a list of resources to be created within stack (e.g. EC2) __MANDATORY__ !
* __conditions__ - specifies if given resources or their parameters are optional during creation or update
* __parameters__ - input values for stack (optional)
* __outputs__ - output values from stack (e.g url to created application, optional)
