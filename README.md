
This repository contains Terraform infrastructure code which creates AWS resources required to run [Atlantis](https://www.runatlantis.io/) on AWS, including:

- Virtual Private Cloud (VPC)
- SSL certificate using Amazon Certificate Manager (ACM)
- Application Load Balancer (ALB)
- Domain name using AWS Route53 which points to ALB
- [AWS Elastic Cloud Service (ECS)](https://aws.amazon.com/ecs/) and [AWS Fargate](https://aws.amazon.com/fargate/) running Atlantis Docker image
- AWS Parameter Store to keep secrets and access them in ECS task natively

Github repositories was configured to post events to Atlantis webhook URL.


## How to use this?

One of the way to do is via:

1. [As a Terraform module](https://github.com/terraform-aws-modules/terraform-aws-atlantis#run-atlantis-as-a-terraform-module)

### Run Atlantis as a Terraform module

This way allows integration with your existing Terraform configurations.

### Provide Atlantis with server yaml configuration

#### Allow GitHub Webhooks Unauthenticated Access

If you are using one of the authentication methods above along with managed GitHub (not self-hosted enterprise version), you'll need to allow unauthenticated access to GitHub's Webhook static IPs:


## Notes

1. Before the Route53 resource could be created. I  purchased a domain name in AWS for a few dollar. 

