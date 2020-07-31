# tim-onboarding
This project has the templates that the clients need to run in order to start using TIM.

## Templates
We currently have 3 cloudformation templates:
1. onboarding_stack.template: this is the main template that should be used in the master account. It creates a role, an event bus rule and assign a Bucket policy to the given bucket. This template is supposed to be used when the client didn't change the default policy that the bucket gets when a new cost and usage report is created;
1. onboarding_stack_no_policy.template: this template does almost the same thing as the previous one, but this one doesn't change the bucket policy. So, in order to give us access to their report bucket the clients also need to manually add a statement to their bucket policy when using this template. This template is supposed to be used when the client already have an existing cost and usage report and is using a bucket policy other than the default one.
1. onboarding_stack_sub.template: this is a simpler template that should be used in the sub-accounts to give us access to that, so we can pull tags, metrics and other stuff from this sub-account as well.
