### IAM
* Watch this video: [IAM Best Practices](https://www.youtube.com/watch?v=_wiGpBQGCjU)
* Docs to read: [IAM Policies Evaluation logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html#policy-eval-denyallow)

* Identity based policy & resource based policy => It's a unit of permissions. Explicit deny overrides allow.
* Identity based policy & permission boundry policy => It's an intersection of permissions. Explicit deny overrides allow.
* Identity based policy & organizations SCPs => It's an intersection of permissions. Explicit deny overrides allow.
* Identity based policy & session policy => It's an intersection of permissions. Explicit deny overrides allow. Creted for fedarated users. Session policies dynamic per request.

**General flow:** Explicit Deny(least privilige rule) -> Organizational SCPs -> Resource-based policies -> Permission-boundries policies -> Session policies -> Identity-based policies

* Only **assume role** operation can have set `DurationSeconds` parameter. No other options possible.

**AWS Managed policy** - use for group of users, for individual users use inline policies. 

**Inline policies** - policy and the principal entity that it's applied to. For example, you want to be sure that the permissions in a policy are not inadvertently assigned to a principal entity other than the one they're intended for. When you use an inline policy, the permissions in the policy cannot be inadvertently attached to the wrong principal entity. In addition, when you use the AWS Management Console to delete that principal entity, the policies embedded in the principal entity are deleted as well. That's because they are part of the principal entity.
