# terraform-aws-docker-instance

Terraform pattern for bootstrapping a Dockerized EC2 workload on AWS. Provisions an EC2 instance, security group with configurable inbound ports, and a `user_data` script that installs Docker and Docker Compose.

**Stack:** Terraform · AWS (EC2, VPC security groups) · HCL · Bash (user_data)

## What this demonstrates

- Parameterised security group with a `dynamic "ingress"` block driven by a `list(number)` of ports
- AMI lookup via `data "aws_ami"` with owner + filter pattern (Amazon Linux family)
- `user_data` templating so the same module can bootstrap differently-named hosts
- Clean `variables.tf` / `outputs.tf` split

## Usage

```hcl
module "docker_ec2" {
  source   = "ofdengiz/docker-instance/aws"
  key_name = "ofdengiz"
}
```

## Notes

Small reference module — intentionally minimal. For my current AWS-on-Terraform work (cross-account S3 + CloudFront + Lambda@Edge) see **[omerdengiz.com](https://omerdengiz.com)**.
