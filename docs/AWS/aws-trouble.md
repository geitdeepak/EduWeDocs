# 🛠️ AWS Labs Troubleshooting Guide

Welcome to the **AWS Troubleshooting Document** for EduWe learners. This guide helps you troubleshoot common AWS issues encountered during hands-on labs, whether you're using the AWS Free Tier, student sandbox, or personal account.

---

## 🔐 1. Cannot Log in to AWS Console

**Issue:** Login fails or shows invalid credentials.  
**Possible Causes:**
- Typo in account ID, IAM username, or password.
- Using root account where IAM login is needed (or vice versa).
- MFA not configured or expired.

**Solution:**
- Use the IAM sign-in URL:  
  `https://<account-alias>.signin.aws.amazon.com/console`
- Double-check IAM user credentials.
- Learn about IAM login:  
  👉 [https://docs.aws.amazon.com/IAM/latest/UserGuide/console.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/console.html)

---

## 📦 2. "Service Not Available in This Region"

**Issue:** Selected service or AMI not available in the selected region.  
**Cause:** AWS services are region-specific.

**Solution:**
- Switch to supported regions like **us-east-1 (N. Virginia)** or **ap-south-1 (Mumbai)**.
- Check service availability:  
  👉 [https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)

---

## 💳 3. AWS Free Tier Exhausted or Not Applied

**Issue:** You get charged or blocked from creating resources.  
**Causes:**
- Free tier limits exceeded.
- Non-eligible instance or service selected.

**Solution:**
- Use free-tier eligible services like `t2.micro`.
- Monitor free tier usage:  
  👉 [https://console.aws.amazon.com/billing/home#/freetier](https://console.aws.amazon.com/billing/home#/freetier)
- Learn more:  
  👉 [https://aws.amazon.com/free](https://aws.amazon.com/free)

---

## 🖥️ 4. EC2 Instance Won’t Start or Stops Unexpectedly

**Issue:** Instance fails to launch or stops on its own.  
**Causes:**
- Quota limits, unsupported instance type, or key pair issues.

**Solution:**
- Choose a free-tier eligible AMI like **Amazon Linux 2**.
- Verify key pair during launch:  
  👉 [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)
- Check service quotas:  
  👉 [https://console.aws.amazon.com/servicequotas/home](https://console.aws.amazon.com/servicequotas/home)

---

## 🔑 5. SSH or RDP Connection Fails

**Issue:** You can’t connect to EC2 instance.  
**Causes:**
- Incorrect security group settings.
- Wrong or missing key pair.
- No public IP assigned.

**Solution:**
- Add inbound rule for **port 22** (SSH) or **3389** (RDP):  
  👉 [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/authorizing-access-to-an-instance.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/authorizing-access-to-an-instance.html)
- Use correct `.pem` file and run:  
  `chmod 400 your-key.pem`
- Ensure **auto-assign public IP** is enabled during instance setup.

---

## 📁 6. Can't Upload Files to S3 Bucket

**Issue:** Upload fails or is denied.  
**Causes:**
- Permissions missing, public access blocked, or large file.

**Solution:**
- Verify IAM policy allows `s3:PutObject`:  
  👉 [https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
- Learn about S3 Block Public Access:  
  👉 [https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html)
- Use AWS CLI for large file uploads:  
  👉 [https://docs.aws.amazon.com/cli/latest/reference/s3/](https://docs.aws.amazon.com/cli/latest/reference/s3/)

---

## 🧾 7. Access Denied While Creating Resources

**Issue:** `AccessDenied` or `UnauthorizedOperation` errors.  
**Causes:**
- IAM user lacks permissions.

**Solution:**
- Admin should assign policies such as `AmazonEC2FullAccess` or `PowerUserAccess`:  
  👉 [https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html)
- View permissions here:  
  👉 [https://console.aws.amazon.com/iam/home#/users](https://console.aws.amazon.com/iam/home#/users)

---

## 🗃️ 8. Missing Key Pair or Key Not Downloaded

**Issue:** Lost `.pem` file after creation.  
**Solution:**
- You **cannot recover** the key later.
- Create a new key pair and instance:  
  👉 [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)
- Alternatively, migrate the volume to a new instance.

---

## 📡 9. VPC/Subnet Not Found or Network Issues

**Issue:** Can't launch resources due to missing VPC/subnet.  
**Cause:** VPC deleted or not configured correctly.

**Solution:**
- Use **default VPC**:  
  👉 [https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html](https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html)
- Create new VPC from console:  
  👉 [https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

---

## 💡 Additional Best Practices

- Always **tag resources** (e.g., `Project=EduWeLab`) for easy tracking.
- Use **CloudShell** for CLI-based tasks:  
  👉 [https://console.aws.amazon.com/cloudshell](https://console.aws.amazon.com/cloudshell)
- Monitor cost and usage:  
  👉 [https://console.aws.amazon.com/billing/home](https://console.aws.amazon.com/billing/home)

---

> 💬 Still stuck? Reach out to your EduWe instructor with:
> - Screenshots
> - Instance ID
> - AWS region
> - Actions performed

---

**Happy Learning on AWS! ☁️🚀**


----
<div style="text-align: center; padding-top: 30px;">
  <img src="/images/logo.png" alt="EduWe Logo" style="max-width: 150px; height: auto;"/>
  
  <center><strong>Ceekh Edunix Pvt Ltd</strong></center><br>
    Address: H-34, Ground Floor, Sector 63, Noida, Uttar Pradesh<br>
    Email: <a href="mailto:info@ceekh.com" style="color: #007bff;">info@ceekh.com</a>
  </p>
  <p style="font-size: 14px; color: #555;"><center>© 2025 EduWe. All rights reserved.| Developed by Deepak Kumar Tyagi </center></p>
</div>