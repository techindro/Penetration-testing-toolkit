# 🏗️ Module 20: Terraform Infrastructure as Code (IaC) Shortcuts

Essential commands with practical examples for Terraform configuration initialization, execution planning, infrastructure provisioning, and state management.

---

## 🟢 Level 1: Easy / Beginner Commands

```bash
# 1. Initialize working directory containing Terraform configuration files
terraform init

# 2. Format Terraform configuration files according to canonical style
terraform fmt

# 3. Validate syntax and structural consistency of Terraform files
terraform validate
```

---

## 🟡 Level 2: Medium / Intermediate Workflow Commands

```bash
# 1. Create an execution plan to preview infrastructure changes
terraform plan

# 2. Apply the execution plan to provision infrastructure resources
terraform apply

# 3. Apply changes automatically without interactive confirmation prompt (-auto-approve)
terraform apply -auto-approve

# 4. View current output variables defined in root module
terraform output
```

---

## 🔴 Level 3: Hard / Advanced State & Destruction Commands

```bash
# 1. List all resources tracked inside current Terraform state file
terraform state list

# 2. Inspect detailed attributes of a specific resource in state
terraform state show aws_s3_bucket.my_app_bucket

# 3. Destroy ALL provisioned infrastructure managed by current configuration
terraform destroy -auto-approve
```
