> ### 📌 Archived reference
>
> Built **2023** during the Clarusway AWS DevOps curriculum. Kept public as a reference for the patterns I use day-to-day.
>
> Terraform pattern for bootstrapping a Dockerized EC2 workload on AWS, including VPC networking and security group configuration.
>
> **Stack:** Terraform · AWS EC2 · Docker · HCL
>
> ➡️ **Current work:** my portfolio at **[https://omerdengiz.com](https://omerdengiz.com)** — a static site on AWS S3 + CloudFront + Lambda@Edge, provisioned with Terraform across two AWS accounts.

---Terraform Module to provision an AWS EC2 instance with the latest amazon linux 2 ami and installed docker in it.

Not intended for production use. It is an example module.

It is just for showing how to create a publish module in Terraform Registry.

Usage:

```hcl

provider "aws" {
  region = "us-east-1"
}

module "docker_instance" {
    source = "<github-username>/docker-instance/aws"
    key_name = "clarusway"
}
```