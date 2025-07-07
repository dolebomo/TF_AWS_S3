# TF_AWS_S3
Terraform AWS S3 cluster
Below are basic resources creation that can be created within Terraform and be deployed without needing to view the management console within AWS.

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-west-2"
}

resource "aws_s3_bucket" "example" {
  bucket = "your-unique-bucket-name"

  tags = {
    Name        = "My example bucket"
    Environment = "Dev"
  }
}
