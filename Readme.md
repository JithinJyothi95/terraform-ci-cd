# Terraform CI/CD with GitHub Actions

## Overview
This project demonstrates how to use GitHub Actions to automate Terraform workflows including initialization, planning, applying, and destroying infrastructure.

## Resources Created
- AWS EC2 instance using the latest Amazon Linux 2 AMI
- Customizable via input variables for `core_count` and `thread_count`

## Files
- `main.tf`: Contains the AWS provider configuration and EC2 instance resource
- `variables.tf`: Declares input variables used in the Terraform configuration
- `.github/workflows/terraform.yml`: GitHub Actions CI/CD pipeline

## CI/CD Features
- Automatic `terraform init`, `validate`, `plan`, and `apply` on push to `main`
- Manual trigger support
- Separate job for manual `terraform destroy`

## Secrets Required
Set the following GitHub repository secrets:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_SESSION_TOKEN`

---

## GitHub Actions CI/CD Summary

This repository demonstrates a working CI/CD pipeline for Terraform using GitHub Actions. The workflow is defined in `.github/workflows/terraform.yml` and performs the following actions:

- Initializes Terraform
- Validates configuration
- Generates an execution plan
- Applies changes (on push to main)
- Supports manual destroy via workflow dispatch

###  Credential Limitation

> The workflow ran successfully up to the `terraform validate` step.  
> The `terraform plan` and `terraform apply` steps failed due to missing AWS credentials, as my AWS Academy account had expired at the time of execution.

Despite this, the GitHub Actions integration was correctly configured and triggered, fulfilling the lab objectives.

---

*By Jithin*
