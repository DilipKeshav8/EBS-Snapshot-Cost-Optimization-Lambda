⚡️ EBS Snapshot Cost Optimization Lambda 💰


🚀 Overview
This project implements a cost optimization solution by automatically identifying and deleting stale Amazon EBS snapshots — snapshots no longer associated with any active EC2 instances. This helps reduce unnecessary AWS storage costs.

The core component is an AWS Lambda function that runs periodically, scans for orphaned snapshots, and deletes them safely. 🧹

✨ Features
🔍 Scans all EBS snapshots owned by your AWS account

🛑 Identifies snapshots not linked to any running or stopped EC2 instance

🗑️ Deletes stale snapshots to free up storage and reduce AWS costs

⚙️ Automated and serverless using AWS Lambda and CloudWatch Events (or EventBridge)

🔧 Easily customizable and extendable

🔎 How It Works
The Lambda function lists all snapshots owned by the account.

It retrieves all active EC2 instances and their associated EBS volumes.

Compares snapshots against volumes currently in use.

Identifies snapshots that do not belong to any active volume.

Deletes the stale snapshots after validation.

🛠️ Prerequisites
AWS account with appropriate permissions:

ec2:DescribeSnapshots

ec2:DescribeInstances

ec2:DescribeVolumes

ec2:DeleteSnapshot

AWS CLI configured or access to the AWS Management Console

Basic knowledge of AWS Lambda and CloudWatch Events/EventBridge

🚀 Deployment
Create an IAM Role with the required permissions above.

Deploy the Lambda function code.

Attach the IAM Role to the Lambda function.

Configure a CloudWatch Event rule (or EventBridge) to trigger the Lambda function on a schedule (e.g., daily or weekly). ⏰

🎯 Usage
Monitor AWS Lambda logs to review actions performed. 📜

Adjust schedule and retention logic as needed for your environment.

Optionally, add SNS notifications for reporting deleted snapshots. 📩

⚠️ Important Notes
❗ Caution: Deleted snapshots cannot be recovered. Make sure your snapshot retention policy aligns with your backup and disaster recovery requirements.

🧪 Test the function in a non-production environment before deploying in production.

📜 License
MIT License


