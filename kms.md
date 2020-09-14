# AWS KMS Keys

![](./kms_key_matrix.png)

1. Region-based service
1. AWS Managed Keys
1. AWS Owned Managed Keys
1. AWS Customer Managed Keys:
      * Key policies - __primary way__ to control access to CMKs. 
          * Default key policy:
              * When using AWS SDK or AWS CLI policy can be definied programatically. If not definied __default__ gives the AWS account (root user) that owns the CMK full access to the CMK and enables IAM policies in the account to allow access to the CMK.
               * When using AWS Console it is possible to choose the IAM users, IAM roles, and AWS accounts that are given access to the CMK.
      * Customer managed CMKs are CMKs in your AWS account that you create, own, and manage. You have full control over these CMKs, including establishing and maintaining their key policies, IAM policies, and grants, enabling and disabling them, rotating their cryptographic material, adding tags, creating aliases that refer to the CMK, and scheduling the CMKs for deletion.
      * Symmetric
      * Asymmeric
      * By __default__ AWS creates __key material__ for CMK, key material can be imported, 
