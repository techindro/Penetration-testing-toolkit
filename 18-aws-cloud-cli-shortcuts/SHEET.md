# ☁️ Module 18: AWS Cloud CLI Shortcuts & One-Liners

Essential command line shortcuts and CLI one-liners for AWS S3, EC2, IAM, and Security Verification with clear practical examples.

---

## ⚡ 1. Configuration & Identity Verification

```bash
# Example 1: Configure AWS CLI credentials and default region
aws configure
# Prompts for AWS Access Key ID, Secret Access Key, Region (e.g. us-east-1), and Output format (json).

# Example 2: Verify active authenticated identity (STS Caller Identity)
aws sts get-caller-identity
# Output: Returns Account ID, User ARN, and User ID.
```

---

## 🪣 2. AWS S3 Storage Operations

```bash
# Example 1: List all S3 buckets in account
aws s3 ls

# Example 2: List contents of a specific S3 bucket recursively
aws s3 ls s3://my-app-bucket/ --recursive --human-readable

# Example 3: Copy local file to S3 bucket
aws s3 cp local_file.txt s3://my-app-bucket/data/local_file.txt

# Example 4: Sync local directory with S3 bucket (Uploads only modified files)
aws s3 sync ./dist/ s3://my-app-bucket/dist/ --delete

# Example 5: Verify anonymous public access to bucket (Security Audit)
aws s3 ls s3://target-bucket-name --no-sign-request
```

---

## 💻 3. AWS EC2 & IAM Operations

```bash
# Example 1: List all EC2 instances with Instance ID, State, and Public IP
aws ec2 describe-instances --query "Reservations[*].Instances[*].[InstanceId,State.Name,PublicIpAddress]" --output table

# Example 2: List all IAM Users in account
aws iam list-users --query "Users[*].[UserName,CreateDate]" --output table
```
