# Automated Website Deployment on AWS EC2 using GitHub Actions

## Project Overview

Built an automated CI/CD pipeline to deploy a static website hosted on an AWS EC2 instance using GitHub Actions and a self-hosted runner.

Whenever changes are pushed to the main branch of the GitHub repository, GitHub Actions automatically triggers a deployment workflow that updates the website on the EC2 instance without requiring manual SSH deployment.

## Architecture

GitHub Repository → GitHub Actions → Self-hosted Runner (EC2) → Apache Web Server → Live Website

## Technologies Used

- **AWS EC2:** Virtual server hosting the website.
- **Amazon VPC:** Custom virtual network for AWS resources.
- **Amazon Linux 2023:** Operating system for the EC2 instance.
- **Apache HTTP Server:** Hosts the static website.
- **GitHub:** Source code management.
- **GitHub Actions:** Automates the deployment process.
- **Self-hosted Runner:** Executes GitHub Actions workflows on EC2.
- **AWS IAM:** Manages EC2 permissions and Systems Manager access.
- **AWS Systems Manager:** Enables remote command execution.

## AWS Infrastructure

- Created a custom VPC.
- Configured public and private subnets.
- Attached an Internet Gateway.
- Configured public routing.
- Launched an EC2 instance in the public subnet.
- Configured security groups for HTTP and restricted SSH access.
- Attached an IAM role with AmazonSSMManagedInstanceCore.
- Registered the EC2 instance with Systems Manager.

## CI/CD Implementation

1. Created a private GitHub repository.
2. Installed and configured a GitHub Actions self-hosted runner on EC2.
3. Configured the runner as a background service.
4. Created a GitHub Actions workflow using YAML.
5. Configured deployment to trigger on pushes to the main branch.
6. Used Apache to serve the updated website.
7. Verified successful deployments through GitHub Actions.

## Deployment Workflow

1. Developer updates index.html.
2. Changes are committed and pushed to GitHub.
3. GitHub Actions detects the push.
4. The self-hosted runner receives the workflow job.
5. The runner checks out the latest repository code.
6. The deployment script copies index.html into Apache's web directory.
7. Apache serves the updated website.

## Key Learning Outcomes

- AWS networking and VPC configuration.
- EC2 instance management.
- Linux administration.
- IAM roles and permissions.
- AWS Systems Manager.
- GitHub Actions and YAML workflows.
- CI/CD pipeline implementation.
- Automated website deployment.
- Troubleshooting deployment failures.

## Project Result

Successfully implemented a working CI/CD pipeline where pushing changes to GitHub automatically updates a live website hosted on AWS EC2.
