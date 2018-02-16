+++
title = "Frontend Service"
chapter = false
weight = 1
+++

Again, we can take advantage of opinionated tooling to deploy our service using best practices.

When a service team wants to build a new service, they can include their own
[mu.yml](https://github.com/brentley/ecsdemo-frontend/blob/master/mu.yml) and inherit
best practices such as blue/green deploys, healthchecks, and autoscaling for their service.

```
---
service:
  desiredCount: 3
  maxSize: 6
  port: 3000
  pathPatterns:
  - /*
  networkMode: awsvpc
  environment:
    BACKEND_API: "http://api.internal.service:80"
```

In this file, we define the service and how it should run. We want a minimum of 3 containers
of our service running, for redundancy.  These will automatically be spread across our 3
availability zones.

Autoscaling will be configured with a maximum of 6 containers.

The containers listen on port 3000, and ALB should be configured to route all paths to
these containers.

We're using _awsvpc_ networking mode, so each container will get it's own ENI.

When each container is launched, it will have a custom environment variable set
so the application knows the URL of the backend api.