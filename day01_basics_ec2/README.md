# 🚀 Day 1 — Terraform Basics: Launch Your First EC2 Instance

This project is part of my 15-Day Terraform Learning Challenge.
On Day 1, we explore Terraform fundamentals and provision a simple EC2 instance on AWS.

🎯 Objectives

Understand the Terraform workflow → init → validate → plan → apply → destroy.

Configure the AWS Provider in Terraform.

Launch a basic EC2 instance with Terraform.

Document real-time issues & solutions.

Build a foundation for interviews & portfolio projects.

📚 Prerequisites
🟢 AWS Basics

EC2 = Virtual server in AWS.

VPC = Virtual network.

Regions & Availability Zones = Physical infra distribution.

🟢 Terraform Basics

IaC (Infrastructure as Code): Manage infra with code.

Why Terraform? Consistency, version control, automation, and multi-cloud support.

🟢 Setup Requirements

AWS Account (Free Tier).

IAM User with programmatic access:

Permissions: AmazonEC2FullAccess, AmazonVPCFullAccess.

Access Key ID + Secret Access Key.

Installed Tools:

Terraform CLI

AWS CLI

Git & VS Code (for coding + GitHub).

🛠️ Step-by-Step Guide
1️⃣ Configure AWS CLI
aws configure
# Provide:
# AWS Access Key ID: <your-key>
# AWS Secret Access Key: <your-secret>
# Default region: ap-south-1
# Default output: json


Verify configuration:

aws sts get-caller-identity

2️⃣ Terraform Workflow
terraform init            # Initialize project (download AWS provider)
terraform validate        # Validate syntax
terraform plan            # Preview infra changes
terraform apply -auto-approve   # Provision EC2 instance
terraform output          # Show instance details (ID, IP)
terraform destroy -auto-approve # Clean up resources

⚡ Real-Time Scenarios

❌ EC2 unreachable (SSH issue):
Cause: No Security Group attached.
Fix: Add SG with port 22 open (covered in Day 4).

❌ Invalid AMI ID:
Cause: AMI IDs are region-specific.
Fix: Use correct AMI for your region.

❌ Invalid credentials:
Cause: IAM user had only console access.
Fix: Create IAM access keys (programmatic access).

📝 Interview Prep Notes

Q: Why use Terraform over manual AWS Console?
A: Repeatability, automation, consistency, and version control.

Q: Explain Terraform workflow.
A: init → validate → plan → apply → manage infra → destroy.

Q: What are Terraform providers?
A: Plugins that enable Terraform to interact with cloud services (AWS, Azure, GCP).