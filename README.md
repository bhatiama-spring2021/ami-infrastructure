# ami-infrastructure
This app is used for attach policies to an IAM user to build AMI on AWS

```
Note: 
- No var file needed to run this terraform
- Create an IAM user with name "ghaction-ami" with programmatic access in your AWS account
- Change the region in provider to your region. eg: us-east-1
```
## Tools used
* [Hashicorp Terraform](https://www.terraform.io/)

## Prerequisites
Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) and [configure CLI profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)

## Installation
### Ubuntu/Debian
Add the HashiCorp GPG key.

    curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

Add the official HashiCorp Linux repository.

    sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

Update and install.

    sudo apt-get update && sudo apt-get install terraform

### Other Operating System
To learn how to install Packer for other OS, click [here](https://learn.hashicorp.com/tutorials/terraform/install-cli)

## Terraform commands
To initialize terraform:

    terraform init

Validate terraform configuration file:

    terraform plan

Execute and create resources:

    terraform apply

Destroy the resources in AWS:

    terraform destroy

Use in-line variables:

    terraform apply -var="foo=bar"

Passing .tfvars file:

    terraform apply -var-file="dev.tfvars"

## Creating multiple VPCs from same .tf file

### Workspace

    terraform workspace
    new, list, show, select and delete Terraform workspaces.

> Note: Terraform uses default workspace when we initialize project with terraform init

Create new workspace using:

    terraform workspace new bar

Switch to different workspace:

    terraform workspace select foo

To learn more about terraform workspace, click [here](https://www.terraform.io/docs/state/workspaces.html)

