# backend.conf

Create Terraform Backend Config.

Create S3 and Dynamo First. Then add in backend config to migrate state to s3
```
terraform {
  backend "s3" {
    # Replace this with your bucket name!
    bucket         = var.bucket_name
    key            = "global/s3/terraform.tfstate"
    region         = "us-east-1"
    # Replace this with your DynamoDB table name!
    dynamodb_table = var.table_name
    encrypt        = true
  }
}
```

## Example tfvars
Uses tfvars file for variables

Example create **terraform.tfvars** file and add

```
bucket_name = "my-terraform-state"

table_name = "my-terraform-state"
```
