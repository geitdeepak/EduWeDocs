# 🚀 **Deployment of WebApp Using Azure App Service**

In today’s cloud-native world, deploying a web application shouldn’t feel like rocket science. Whether you're a student building your first project or a professional scaling apps for production, **Azure App Service** makes web deployment **simple, fast, and powerful**.

Let’s walk through how you can deploy a sample web application from GitHub or your local machine using Azure App Service—and take it further with deployment slots, auto-scaling, and monitoring through Application Insights.

![architecture](/media/blog36.png)

---

## 🌐 What is Azure App Service?

Azure App Service is a **fully managed platform for hosting web applications, REST APIs, and mobile backends**. It supports multiple programming languages like .NET, Java, Node.js, Python, and PHP—so you can bring your app and let Azure handle the infrastructure, scaling, and availability.

**Benefits:**
- Zero infrastructure setup  
- Built-in CI/CD integration with GitHub, Azure DevOps, Bitbucket  
- Auto-scaling and high availability  
- Custom domain and SSL support  
- Integrated monitoring via Azure Application Insights  

---

## 🛠️ Step-by-Step: Deploying a WebApp from GitHub

Let’s deploy a sample web application (e.g., a basic Node.js or Python app) from GitHub:

### ✅ Prerequisites:
- Azure account ([Create free account](https://azure.microsoft.com/free/))  
- A sample app on GitHub (or use [Microsoft’s sample](https://github.com/Azure-Samples))

### 🔧 Steps:

1. **Login to Azure Portal**  
   - Visit [portal.azure.com](https://portal.azure.com)  

   ![Login](/media/blog31.png)

   - Go to “App Services” > Click **“Create”**

   ![create weapp](/media/blog32.png)

2. **Fill in the App Details**  
   - Resource Group: `MyWebApp-RG`  
   - Name: `mywebapp123` (must be globally unique)  
   - Runtime stack: Choose your language (e.g., Node.js 18 LTS)  
   - Region: Select your nearest data center

3. **Choose Deployment Option**  
   - Under the **Deployment** tab, select **GitHub**  
   - Authenticate your GitHub account  
   - Select the repository and branch (e.g., `main`)

4. **Review and Create**  
   - Review configuration  
   - Click **“Create”** and wait for deployment to finish  
   - Once complete, click **“Browse”** to open your web app 🎉

---

## 🔄 Set Up Deployment Slots (Staging vs Production)

Azure allows you to create **deployment slots**—separate environments for staging and production under the same app service.

### Why Use Slots?
- Test your app in staging before pushing to production  
- Swap between staging and production with zero downtime

### How to Add a Slot:
1. Go to your App Service > **Deployment Slots**  
2. Click **“Add Slot”**  
3. Name it `staging`, choose to clone settings from the production slot  
4. Deploy your app to `staging`, test it, and then **swap** when ready
 
 ![slots](/media/blog34.png)
---
## 📈 Enable Auto-Scaling

Don’t let success crash your app! Azure App Service lets you scale automatically based on CPU, memory, or request count.

### To Enable Auto-Scaling:
1. Go to your App Service > **Scale out (App Service Plan)**  
2. Choose a scaling rule (e.g., scale out if CPU > 70%)  
3. Define minimum and maximum instances

 ![scaling](/media/blog35.png)

Azure will now manage the scaling for you—keeping performance smooth even under pressure.

---

## 📊 Monitor Health with Application Insights

You can’t fix what you can’t measure. With **Application Insights**, you can monitor:

- Response times  
- Server exceptions  
- Usage metrics  
- Live metrics streaming

### How to Enable:
1. Go to App Service > **Application Insights**  
2. Click **“Enable”**  
3. Once enabled, view metrics and logs from the same panel

----

### Browse Final deployed WebApp in your any Browser:

 ![webapp](/media/blog33.png)
## 💡 Final Thoughts

Deploying a web application is just the beginning—but doing it with Azure App Service means you’re future-ready from day one.

From setting up in minutes to testing with slots, scaling automatically, and keeping track of everything with Application Insights, **you have enterprise-grade tools at your fingertips**.

So whether you're pushing your first web app or launching something for millions—Azure App Service is your launchpad.

**Ready to deploy?** Start with your GitHub project or local code, and make the cloud your playground.

----
<div style="text-align: center; padding-top: 30px;">
  <img src="/media/logo.png" alt="EduWe Logo" style="max-width: 150px; height: auto;"/>
  
  <center><strong>Ceekh Edunix Pvt Ltd</strong></center><br>
    Address: H-34, Ground Floor, Sector 63, Noida, Uttar Pradesh<br>
    Email: <a href="mailto:info@ceekh.com" style="color: #007bff;">info@ceekh.com</a>
  </p>
  <p style="font-size: 14px; color: #555;"><center>© 2025 EduWe. All rights reserved.| Developed by Deepak Kumar Tyagi </center></p>
</div>