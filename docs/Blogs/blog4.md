# ⚖️ **Load Distribution Using Azure Load Balancer**

In the cloud world, **performance, availability, and reliability** are non-negotiable—especially when your application is serving thousands of users across different geographies. This is where **Azure Load Balancer** becomes a hero behind the scenes.

Just like a traffic cop directing vehicles to different lanes, **Azure Load Balancer** intelligently distributes incoming traffic across multiple virtual machines (VMs) to ensure no single machine gets overloaded.

In this blog, you’ll learn how to configure and test traffic distribution using **Azure Load Balancer** (Basic or Standard). We’ll walk through backend pools, health probes, and load balancing rules—all with simple steps and analogies to help you understand the ***why*** and ***how***.

---

## 🚦 What is Azure Load Balancer?

Azure Load Balancer is a **Layer 4 (TCP/UDP) load balancer** that automatically distributes network traffic across multiple backend resources like VMs or virtual machine scale sets.

### Types of Azure Load Balancers:
- **Basic Load Balancer**: Ideal for dev/test or single-region apps.
- **Standard Load Balancer**: Production-ready, secure, and zone-redundant—supports more features like higher scalability and metrics.

![Public Load Balancer](/media/blog44.png)

---

## 🧠 Analogy: Load Balancer as a Restaurant Host

Imagine a busy restaurant with several servers. A host greets each guest and decides which table (server) they should go to, depending on who’s available and how busy they are. Azure Load Balancer does the same—it receives incoming traffic and forwards it to the least busy and healthy backend instance.

![Analogy](/media/blog41.png)

---

## 🛠️ Core Components

Before jumping into the configuration, let’s understand the 3 key pieces of an Azure Load Balancer:

### 1. **Backend Pool**
A group of virtual machines or instances that will serve the traffic.

### 2. **Health Probes**
These check the health of each VM in the backend pool (using protocols like TCP or HTTP). If a VM fails, it is automatically removed from traffic rotation.

### 3. **Load Balancing Rules**
Rules that define how incoming traffic is distributed. You can control port mapping, protocol, and session persistence.

---

## ⚙️ Step-by-Step: Configure Azure Load Balancer

### ✅ Prerequisites:
- Two or more VMs in the same Azure Virtual Network (VNet)
- Azure Subscription
- Basic understanding of Azure Networking

---

### 🔧 Step 1: Create the Load Balancer

1. Go to the Azure Portal > Search for **Load Balancer**
2. Click **Create**
3. Select:
   - **Standard** or **Basic**
   - Public or Internal (based on your use case)
4. Choose your Resource Group and Region

![Create Load Balancer](/media/blog45.png)

---

### 🔗 Step 2: Define the Backend Pool

1. After creation, go to **Backend Pools** under your load balancer
2. Click **Add**
3. Select the virtual machines (VM1, VM2...) you want to include

![backend pool](/media/blog42.png)

---

### 💓 Step 3: Configure Health Probes

1. Go to **Health Probes** > Click **Add**
2. Choose the protocol (TCP/HTTP)
3. Set port (e.g., 80 for HTTP) and interval settings
4. Azure will use this to monitor VM health continuously

---

### 📜 Step 4: Set Load Balancing Rules

1. Go to **Load Balancing Rules** > Click **Add**
2. Set:
   - Frontend IP (your load balancer IP)
   - Backend port and protocol
   - Session persistence (optional)
   - Associate with health probe and backend pool

![healthprobe](/media/blog43.png)

---
### 🌐 Step 5: Install IIS on Azure Virtual Machines

Follow the steps below to install IIS and set up a custom `iisstart.htm` file on Azure VMs.

---

### 🔹 Open Virtual Machine

1. In the search bar at the top of the Azure portal, type **Virtual machine**.
2. Select **Virtual machines** from the search results.
3. Click on **VM1**.

---

### 🔹 Connect via Bastion

1. On the **Overview** page, click **Connect**, then choose **Bastion**.
2. Enter the **username** and **password** used during the VM's creation.
3. Click **Connect**.

---

### 🔹 Install IIS using PowerShell

1. On the server desktop, go to:  
   **Start > Windows PowerShell > Windows PowerShell**
2. In the PowerShell window, run the following commands:

   >  
   
   
      # Install IIS server role
      Install-WindowsFeature -name Web-Server -IncludeManagementTools

      # Remove default htm file
      Remove-Item  C:\inetpub\wwwroot\iisstart.htm

      # Add a new htm file that displays server name
      Add-Content -Path "C:\inetpub\wwwroot\iisstart.htm" -Value $("Hello World from " + $env:computername)

Close the Bastion session with **VM1**.

Repeat **steps 1 to 8** to install IIS and the updated iisstart.htm file on **VM2**.

---
### 🧪 Step 6: Test Load Balancing

1. Open the frontend public IP in a browser or run curl commands
2. Azure will route requests to available healthy VMs
3. Stop one VM and reload—traffic is redirected to the healthy one (thanks to health probes!)

![Test Load Balancer](/media/blog46.png)

---

## 📈 Bonus: Monitoring and Metrics

Use **Azure Monitor** or **Log Analytics** to:

- View traffic distribution
- Monitor health probe status
- Analyze dropped packets or latency issues

---

## 💡 Final Thoughts

Azure Load Balancer ensures your application remains **resilient, highly available, and responsive**. By distributing traffic smartly and continuously monitoring VM health, it prevents performance bottlenecks and downtime.

Whether you’re building a cloud-native app, a high-traffic website, or running enterprise backend services—**load balancing is essential**. And with Azure, it’s easier than ever to configure, monitor, and scale.

So go ahead—deploy your VMs, configure Azure Load Balancer, and let the cloud handle the traffic.

----
<div style="text-align: center; padding-top: 30px;">
  <img src="/images/logo.png" alt="EduWe Logo" style="max-width: 150px; height: auto;"/>
  
  <center><strong>Ceekh Edunix Pvt Ltd</strong></center><br>
    Address: H-34, Ground Floor, Sector 63, Noida, Uttar Pradesh<br>
    Email: <a href="mailto:info@ceekh.com" style="color: #007bff;">info@ceekh.com</a>
  </p>
  <p style="font-size: 14px; color: #555;"><center>© 2025 EduWe. All rights reserved.| Developed by Deepak Kumar Tyagi </center></p>
</div>