# End-to-End Cloud Resource Monitoring Automation

This project automates the process of listing active AWS resources (e.g., EC2, S3) using a shell script. It helps DevOps teams monitor resource usage and optimize costs.

## Overview

### Objective
Automate the process of listing active AWS resources (e.g., EC2, S3) using a shell script.

### Why
- DevOps Engineers need such scripts to monitor resource usage for cost optimization.
- Helps in day-to-day operations and automation workflows like cron jobs.

### Key Concepts

- **Purpose of Shell Scripting in DevOps**:
  - Automates repetitive tasks.
  - Ensures consistency in operations like listing, monitoring, or resource management.
  
- **What the Script Does**:
  - Connects to AWS.
  - Lists active resources for specified services (e.g., EC2, S3).
  - Takes two inputs: region and service.
  
- **Inputs and Outputs**:
  - **Inputs**: AWS region and service name (e.g., `us-east-1`, `ec2`).
  - **Output**: Lists all active resources for the specified service in the given region.

## Steps to Build the Script

### Setup
- **Editor**: Use VS Code to write the script.
- **Environment**: Use an AWS EC2 instance to run and test the script (preferred for Windows users).

### Script Outline
1. **Start with comments**:
   - Purpose: "This script lists active AWS resources."
   - Author info (e.g., your name, team).
   - Versioning for tracking updates (e.g., v0.1).

2. **Validations**:
   - Check if required arguments (region and service) are provided.
   - Verify that AWS CLI is installed and configured.

3. **Core Logic**:
   - Use AWS CLI to interact with AWS services.
   - Validate supported services (e.g., EC2, S3, EBS) and reject invalid inputs.
   - Use `switch-case` for better performance over `if-else`.

4. **Command Execution**:
   - Example for EC2: `aws ec2 describe-instances`.
   - Example for S3: `aws s3api list-buckets`.

5. **Security Best Practices**:
   - Limit script permissions using `chmod` (e.g., `chmod 711`).

## Steps to Run the Script

1. Install AWS CLI and configure it using `aws configure`.
2. Execute the script:
   ```bash
   ./aws_resource_list.sh <region> <service>
