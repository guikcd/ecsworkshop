+++
title = "Acceptance and Production"
chapter = false
weight = 7
+++

Let's bring up the Acceptance and Production environments!

Copy/Paste the following commands into your Cloud9 workspace:

```
cd ~/environment/ecsdemo-platform
mu env up acceptance && mu env up production
```
Watch what is being built in [CloudFormation](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks)
{{% notice tip %}}
This will take 20 minutes
{{% /notice %}}

Now lets bring up the CodePipeline for maintaining our infrastructure:
```
mu pipeline up
```
Paste your personal GitHub token
This builds the CI/CD CodePipeline that will manage infrastructure code changes

{{% notice tip %}}
This will take 10 minutes
{{% /notice %}}