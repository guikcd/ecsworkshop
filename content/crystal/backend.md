+++
title = "Deploy the Backend Pipeline"
chapter = false
weight = 2
+++

Let’s bring up the Crystal Backend API!

Copy/Paste the following commands into your Cloud9 workspace:

```
cd ~/environment/ecsdemo-crystal
mu pipeline up
```
Paste your personal GitHub token

{{% notice tip %}}
This will take 5 minutes
{{% /notice %}}

After the CodePipeline is built, [watch it run](https://console.aws.amazon.com/codepipeline/home?region=us-east-1#/view/mu-ecsdemo-crystal)

You can also follow the logs:
```
mu pipeline logs -f
```