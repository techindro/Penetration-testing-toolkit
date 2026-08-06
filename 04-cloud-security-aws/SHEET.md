# ☁️ Module 04: Cloud Security Architecture (AWS)

This module details AWS security models, S3 storage permission policies, EC2 metadata protection, and AWS CLI tool flags.

---

## 📐 1. Technical Concepts & Cloud Access Models

### A. AWS S3 Access Control Evaluation Logic
Access to AWS S3 storage assets is evaluated dynamically across bucket policies, IAM policies, and Access Control Lists (ACLs):

$$\text{Final Access Permission} = (\text{Explicit Allow}) \land \neg (\text{Explicit Deny})$$

If an S3 bucket policy grants `s3:GetObject` to Principal `*` without condition blocks, any unauthenticated web user can read bucket contents.

### B. Instance Metadata Service Versioning (IMDSv1 vs IMDSv2)

#### Legacy IMDSv1 Mechanics (Vulnerable to SSRF)
IMDSv1 utilizes simple GET requests without authentication headers to retrieve temporary IAM instance credentials:

$$\text{Request: } \text{GET } \text{http://169.254.169.254/latest/meta-data/iam/security-credentials/role-name}$$

#### Hardened IMDSv2 Mechanics (Token-Based Session)
IMDSv2 enforces session-oriented HTTP PUT request token acquisition with HTTP header validation:

$$\text{Step 1 (Token Fetch): } \text{PUT /latest/api/token } \xrightarrow{\text{Header: X-aws-ec2-metadata-token-ttl-seconds: 21600}} \text{Token } T$$

$$\text{Step 2 (Data Fetch): } \text{GET /latest/meta-data/ } \xrightarrow{\text{Header: X-aws-ec2-metadata-token: } T} \text{Metadata Response}$$

Because web application SSRF vulnerabilities rarely forward custom HTTP headers during basic `GET` exploitation, IMDSv2 prevents metadata credential exfiltration.

---

## 🛠️ 2. Core Tool Breakdown (AWS CLI)

```bash
aws s3 ls s3://target-bucket-name --no-sign-request --region us-east-1
```

### Parameter Breakdown:
- `s3 ls` : List objects and directories inside the specified S3 bucket URI.
- `--no-sign-request` : Do not attach local AWS API credentials (tests for public unauthenticated read access).
- `--region <region>` : Specify explicit AWS region endpoint.

---

## 🛡️ 3. Cloud Hardening Checklist
- **Block Public Access:** Enable AWS S3 Block Public Access globally at the AWS Account level.
- **Enforce IMDSv2:** Set EC2 Instance Metadata options to `HttpTokens=required` and `HttpPutResponseHopLimit=1`.
