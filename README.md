# GitLab CI/CD Pipeline for EKS Deployment

This repository contains a GitLab CI/CD pipeline configuration for deploying a given version of an application to an Amazon Elastic Kubernetes Service (EKS) cluster. The pipeline utilizes GitLab's managed Terraform and HTTP backend for secure storage of the Terraform state file.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Configuration](#configuration)
- [Usage](#usage)
- [Pipeline Stages](#pipeline-stages)
- [Environments](#environments)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This GitLab CI/CD pipeline is designed to automate the deployment of your application to an AWS EKS cluster. It leverages GitLab's CI/CD capabilities and Terraform for infrastructure provisioning. Key features of this pipeline include secure state management, environment-specific deployments, and built-in Terraform plan and apply stages.

## Features

1. **Infrastructure as Code (IaC)**: Utilizes GitLab's managed Terraform for infrastructure provisioning, ensuring a consistent and version-controlled approach.

2. **Secure Terraform State Management**: Uses GitLab's managed HTTP backend for storing Terraform state securely, preventing accidental exposure of sensitive information.

3. **Multi-Environment Support**: Configurable for deploying to multiple environments (e.g., test and production) using GitLab's pipeline schedule variables.

4. **AWS EKS Deployment**: Specifically tailored for deploying applications to Amazon EKS clusters.

5. **Built-in CI/CD Stages**: Includes Terraform plan and apply stages in the GitLab CI/CD pipeline for infrastructure changes.

6. **Everything in `.gitlab-ci.yml`**: The entire pipeline configuration is defined in the `.gitlab-ci.yml` file, making it easy to manage and version control.

## Getting Started

Follow these steps to get started with deploying your application using this GitLab CI/CD pipeline:

### Prerequisites

Before using this pipeline, ensure you have the following prerequisites in place:

- A GitLab account and repository set up.
- AWS credentials and necessary permissions for deploying to EKS.
- Your application code and necessary Terraform configurations.

### Configuration

1. Clone this repository to your local machine.

2. Customize the `.gitlab-ci.yml` file to match your specific deployment requirements, including Terraform configurations, environment variables, and AWS credentials.

3. Commit and push the changes to your GitLab repository.

4. Configure your GitLab project's CI/CD settings to use the `.gitlab-ci.yml` file for pipeline configuration.

## Usage

Once the pipeline is configured to trigger the pipeline manually. You can also configure it to trigger a GitLab CICD piepline when new changes are merged into master branch.

## Pipeline Stages

The GitLab CI/CD pipeline includes the following stages:

1. **Terraform Plan**: This stage runs `terraform init` and `terraform plan` to preview the changes to be applied to the infrastructure. It helps identify any potential issues before applying changes.

2. **Terraform Apply**: If the plan stage succeeds and is manually approved or configured to auto-apply, this stage runs `terraform apply` to provision or update the infrastructure.

## Environments

This pipeline supports multiple environments (e.g., test and production) using GitLab's pipeline schedule variables. You can configure these variables to target specific AWS EKS clusters or environments.

## Contributing

Contributions to improve this GitLab CI/CD pipeline configuration are welcome. If you encounter issues or have suggestions for enhancements, please open an issue or submit a merge request following our [contribution guidelines](CONTRIBUTING.md).

## License

This project is licensed under the [MIT License](LICENSE), which allows you to use and modify the pipeline configuration as needed.
