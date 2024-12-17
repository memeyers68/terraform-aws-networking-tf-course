# terraform-aws-networking-tf-course
Networking module created during a TF course on Udemy

This modules manages the creation of VPCs and Subnects, allowing for the creation of both private and public subnets.

Example usage:
```
module "vpc" {
    source = "./modules/networking"
    vpc_config = {
        cidr_block = "10.0.0.0/16"
        name       = "your_vpc"
    }

    subnet_config = {
        subnet_1 = {
        cidr_block = "10.0.0.0/24"
        az         = "us-east-2a"
        }

        subnet_2 = {
        cidr_block = "10.0.1.0/24"
        public     = true
        az         = "us-east-2b"
        }
    }
}

```