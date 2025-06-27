# 🛠️ GCP Labs Troubleshooting Guide

Welcome to the **GCP Troubleshooting Document** for EduWe learners. This guide provides common errors and practical solutions faced during GCP lab sessions, especially for beginners and intermediate users.

---

## 🔐 1. Can’t Log in to Google Cloud Console

**Issue:** Invalid credentials or authentication errors  
**Possible Causes:**
- Incorrect Google account (e.g., personal vs. student account)
- Expired session or 403 error due to lack of access

**Solution:**
- Use the correct Google account provided for labs.
- Try logging in from: [https://console.cloud.google.com](https://console.cloud.google.com)
- Clear browser cookies or switch browser if issues persist.

---

## 🔄 2. “You don’t have permission” Error

**Issue:** Cannot access services or create resources  
**Causes:**
- IAM role does not allow specific actions
- Lab permissions have expired

**Solution:**
- Check IAM roles from **IAM & Admin > IAM**
- Make sure your role includes required permissions like `Editor` or `Owner`
- Refer to GCP IAM roles: [https://cloud.google.com/iam/docs/understanding-roles](https://cloud.google.com/iam/docs/understanding-roles)

---

## 💰 3. “Billing Account Required” or Quota Error

**Issue:** Cannot create resource due to billing or quota issues  
**Causes:**
- Project not linked to billing
- Free trial credits exhausted
- Quota limits reached

**Solution:**
- Link your project to a billing account (if using personal GCP)
- Check quotas from: **IAM & Admin > Quotas**
- Visit [https://console.cloud.google.com/billing](https://console.cloud.google.com/billing)

---

## 🖥️ 4. VM Instance Creation Fails

**Issue:** Unable to create a Compute Engine VM  
**Possible Causes:**
- Insufficient quota
- Unsupported machine type or region
- API not enabled

**Solution:**
- Use `e2-micro` or `n1-standard-1` for free tier
- Choose zones like `us-central1-a` or `asia-south1-a`
- Enable Compute Engine API from:  
  [https://console.cloud.google.com/apis/library/compute.googleapis.com](https://console.cloud.google.com/apis/library/compute.googleapis.com)

---

## 🔐 5. SSH to VM Fails (Timeout or Permission Denied)

**Issue:** You can’t connect to a running instance via SSH  
**Possible Causes:**
- Firewall rules not open
- OS Login not enabled or key issues

**Solution:**
- Go to **VPC Network > Firewall** and ensure port 22 is open
- Use **Browser SSH** for simpler login
- Add your SSH key to the instance if using local SSH
- Use this doc: [https://cloud.google.com/compute/docs/troubleshooting/troubleshooting-ssh](https://cloud.google.com/compute/docs/troubleshooting/troubleshooting-ssh)

---

## 🗄️ 6. GCS Bucket Access Denied

**Issue:** Cannot upload, download or list files in a bucket  
**Possible Causes:**
- IAM permissions missing
- Uniform bucket-level access misconfigured

**Solution:**
- Go to **Cloud Storage > Buckets > Permissions**
- Ensure you have `Storage Object Admin` or higher
- Learn more here: [https://cloud.google.com/storage/docs/access-control](https://cloud.google.com/storage/docs/access-control)

---

## 🧱 7. API Not Enabled Error

**Issue:** Certain services not working or blocked  
**Cause:** Required APIs are not enabled for the project

**Solution:**
- Go to **APIs & Services > Library** and search for the API
- Enable APIs like:
  - Compute Engine API
  - Cloud Storage API
  - Cloud Functions API
- Direct link to enable:  
  [https://console.cloud.google.com/apis/library](https://console.cloud.google.com/apis/library)

---

## 🌍 8. Resource Not Available in Region

**Issue:** Unable to create services like Cloud Run, Functions, etc.  
**Cause:** Region or zone does not support selected service

**Solution:**
- Refer to region-specific availability:  
  [https://cloud.google.com/about/locations](https://cloud.google.com/about/locations)
- Choose widely supported regions like `us-central1`, `us-east1`, `asia-south1`

---

## 🔐 9. “403 PERMISSION_DENIED” When Using CLI or Terraform

**Issue:** Permission denied even after login  
**Possible Causes:**
- gcloud not authenticated
- Wrong project selected

**Solution:**
- Run: `gcloud auth login`
- Set project using:  
  `gcloud config set project <PROJECT_ID>`
- Make sure required APIs are enabled

---

## 💡 Helpful Tips

- Use GCP **Cloud Shell** for easy CLI usage.
- Tag and name your resources properly.
- Always check quotas and roles before starting a new lab.
- To report issues, share:
  - Project ID
  - Region
  - Screenshot of error
  - Services used

---

## 📚 Official Troubleshooting Links

- [GCP Common Issues Guide](https://cloud.google.com/docs/troubleshooting/)
- [GCP Support Center](https://cloud.google.com/support)
- [IAM Troubleshooting](https://cloud.google.com/iam/docs/troubleshooting)
- [Billing & Free Tier FAQs](https://cloud.google.com/free/docs/gcp-free-tier)

---

**Happy Cloud Learning on GCP! ☁️🧠**

----
<div style="text-align: center; padding-top: 30px;">
  <img src="/media/logo.png" alt="EduWe Logo" style="max-width: 150px; height: auto;"/>
  
  <center><strong>Ceekh Edunix Pvt Ltd</strong></center><br>
    Address: H-34, Ground Floor, Sector 63, Noida, Uttar Pradesh<br>
    Email: <a href="mailto:info@ceekh.com" style="color: #007bff;">info@ceekh.com</a>
  </p>
  <p style="font-size: 14px; color: #555;"><center>© 2025 EduWe. All rights reserved.| Developed by Deepak Kumar Tyagi </center></p>
</div>