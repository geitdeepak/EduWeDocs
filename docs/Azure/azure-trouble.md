# 🛠️ Azure Labs Troubleshooting Guide

Welcome to the **Azure Troubleshooting Document**. This guide provides solutions to common problems that learners might face during Azure Labs. Whether you’re a beginner or experienced, this document will help you stay on track and troubleshoot effectively.

---

## ⚙️ 1. Unable to Sign in to Azure Portal

**Issue:** Login fails or redirects unexpectedly.  
**Possible Causes:**
- Incorrect credentials or expired password.
- Multi-Factor Authentication (MFA) enabled.
- Wrong tenant selection.

**Solution:**
- Reset your password using Microsoft account recovery.
- Try logging in with incognito/private browser mode.
- Ensure you are selecting the correct **directory/tenant** after login (top-right corner).

---

## 🌐 2. Subscription Not Visible / "You don't have any subscriptions"

**Issue:** Azure shows no available subscriptions to create or manage resources.  
**Possible Causes:**
- Azure for Students subscription expired or not activated.
- You're in the wrong directory.

**Solution:**
- Go to `https://portal.azure.com/#settings/directory` and switch to the correct directory.
- Check with your institution or Microsoft Learn portal if your subscription is still valid.

---

## 🏗️ 3. Resource Deployment Fails

**Issue:** ARM templates, VMs, or services fail to deploy.  
**Possible Causes:**
- Incorrect region selection.
- Quota exceeded.
- Incomplete or invalid parameters.

**Solution:**
- Always select a region like **East US** or **West Europe** with full service availability.
- Go to **Help + support > Quotas** to check resource limits.
- Double-check your JSON/YAML parameters.

---

## 🧱 4. Virtual Machine (VM) Creation Issues

**Issue:** VM provisioning stuck, failed, or SSH/RDP access not working.  
**Possible Causes:**
- Port 22 (Linux) or 3389 (Windows) not opened in NSG.
- Using unsupported image or size.
- Username format is invalid (like “admin” or “test”).

**Solution:**
- Use VM sizes like `Standard_B1s` for Students.
- Allow necessary inbound rules in **Network Security Group (NSG)**.
- Use acceptable usernames and passwords (avoid “admin”).

---

## 🔐 5. Access Denied / Insufficient Permissions

**Issue:** Cannot create resources, assign roles, or access some features.  
**Possible Causes:**
- Role-Based Access Control (RBAC) not properly set.
- You’re a **Reader**, not an **Owner** or **Contributor**.

**Solution:**
- Ask admin/teacher to grant **Contributor** role.
- Use **Access Control (IAM)** blade to verify permissions.

---

## 💸 6. "Quota Limit Exceeded" Error

**Issue:** You're unable to create VMs or other services due to hitting limits.  
**Possible Causes:**
- Student subscriptions have strict quotas.
- Too many resources provisioned.

**Solution:**
- Delete unused VMs, disks, and public IPs.
- Use smaller VM sizes (e.g., `Standard_B1s`).
- Wait for quota to reset or request an increase (if possible).

---

## 🗺️ 7. Wrong Region Selected

**Issue:** Services not available or pricing different.  
**Solution:**
- Stick to supported regions like **East US**, **West Europe**, or **Central India**.
- Avoid regions with limited availability in student subscriptions.

---

## 🌐 8. DNS or Internet Issues in VM

**Issue:** VM cannot access the internet.  
**Possible Causes:**
- No public IP or DNS settings misconfigured.

**Solution:**
- Assign a public IP during VM creation.
- Check VM’s **Network Interface > DNS servers** setting.

---

## 📄 9. Markdown or Portal Display Issues

**Issue:** Docs not rendering or Azure Portal UI breaks.  
**Solution:**
- Clear cache or use a different browser.
- Use **Edge** or **Chrome** for best Azure portal experience.

---

## 🧪 10. Lab Resources Disappear

**Issue:** VMs or resources get deleted automatically.  
**Cause:** Student subscriptions are temporary or auto-cleaned by IT policy.

**Solution:**
- Always back up lab work locally or in GitHub.
- Complete labs within the given time frame.

---

## 💡 Additional Tips

- Use the **Azure Cloud Shell** for scripting without local setup.
- Save your **Resource Group names** and **subscription details** in a notepad.
- Document your steps — helps when redoing labs or reporting issues.

---

> 📌 Still Stuck? Reach out to your mentor or instructor via the EduWe support system. Include screenshots and steps followed to help us resolve faster.

---

Happy Learning! 🚀
----
<div style="text-align: center; padding-top: 30px;">
  <img src="/media/logo.png" alt="EduWe Logo" style="max-width: 150px; height: auto;">
  <p>
  <center><strong>Ceekh Edunix Pvt Ltd</strong></center><br>
    Address: H-34, Ground Floor, Sector 63, Noida, Uttar Pradesh<br>
    Email: <a href="mailto:info@ceekh.com" style="color: #007bff;">info@ceekh.com</a>
  </p>
  <p style="font-size: 14px; color: #555;"><center>© 2025 EduWe. All rights reserved.| Developed by Deepak Kumar Tyagi </center></p>
</div>