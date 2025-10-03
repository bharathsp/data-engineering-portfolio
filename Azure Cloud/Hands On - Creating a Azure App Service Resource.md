Let me walk you through **step-by-step** on how to create an **Azure App Service** (used to host web apps, REST APIs, and mobile backends).

---

# 🌐 Steps to Create an Azure App Service

### **1. Sign in to Azure Portal**

* Go to 👉 [Azure Portal](https://portal.azure.com).
* Make sure you are in the right **subscription**.

---

### **2. Create a Resource Group (if you don’t have one)**

* In the search bar, type **Resource Groups** → **+ Create**.
  <img width="715" height="218" alt="image" src="https://github.com/user-attachments/assets/4825f282-144b-4758-a7b3-8c4385dad059" />
  <img width="773" height="249" alt="image" src="https://github.com/user-attachments/assets/b1a7df7d-09c2-4901-85c3-217c4fbf6476" />

* Choose:

  * **Subscription**
  * **Resource Group name** (e.g., `my-rg-app`)
  * **Region** (where your resources will be hosted, e.g., Central India / East US).
* Click **Review + Create → Create**. <br>
  <img width="529" height="938" alt="image" src="https://github.com/user-attachments/assets/1e5b550d-2c01-4a76-bce3-58c9051404f7" />
  <img width="861" height="341" alt="image" src="https://github.com/user-attachments/assets/a87399b6-363b-4a76-ae6e-28fc158fe761" />


👉 *Resource Groups help you manage related resources together.*

---

### **3. Create an App Service**

* In the search bar, type **App Services** → **+ Create**.
  <img width="634" height="151" alt="image" src="https://github.com/user-attachments/assets/08046959-86d2-43e9-a782-6030f08c858f" />
  <img width="577" height="220" alt="image" src="https://github.com/user-attachments/assets/ca0108a7-3e05-4a29-985d-66a1c46f38ae" />
  <img width="143" height="137" alt="image" src="https://github.com/user-attachments/assets/62a5d3a9-3e1c-4f26-8dc1-bb2442cdcdea" />

* You’ll see a **wizard with 5 tabs** (Basics, Deployment, Networking, Monitoring, Tags).
<img width="554" height="386" alt="image" src="https://github.com/user-attachments/assets/db06dfd4-1be2-40bf-a2dc-aeb690f87f78" />

---

### **4. Fill in Basics**

* **Subscription** → choose your Azure subscription.
* **Resource Group** → select existing or create new.
* **Name** → enter a unique name for your app (this becomes part of your URL, e.g., `myapp.azurewebsites.net`).
* **Publish** → choose:

  * **Code** (if you’ll deploy source code, e.g., Python/Node.js/Java/.NET)
  * **Docker Container** (if deploying via Docker image)
  * **Static Web App** (for static HTML/JS/CSS, but usually separate service)
* **Runtime stack** → choose the technology (e.g., Node.js, .NET, Java, Python, PHP).
* **Operating System** → Linux or Windows (Linux is cheaper and recommended for most stacks).
* **Region** → choose a region close to your users.
* **App Service Plan** →

  * Click **Create new** → give it a name.
  * Choose **Pricing plan** (e.g., Free F1 for testing, B1 for basic, P1v2 for production).

---

### **5. Configure Deployment (Optional)**

* Tab: **Deployment**
* You can link a **GitHub repo**, **Azure Repos**, or use **manual deployment**.
* If you skip now, you can configure CI/CD later.

---

### **6. Networking (Optional)**

* Choose whether the app should have **public access** or integrate with a **VNet**.
* By default → leave as public.

---

### **7. Monitoring**

* Enable **Application Insights** (recommended) to collect logs, performance data, and failures.
* Choose region for Insights (ideally same as App Service region).

---

### **8. Tags (Optional)**

* Add tags for cost tracking (e.g., `Dept=Finance`, `Project=WebApp`).

---

### **9. Review + Create**

* Azure will validate your settings.
* Click **Create**.
* Deployment takes a few minutes.

---

### **10. Access Your App**

* Once deployment finishes, go to **App Services → Your App → Overview**.
* You’ll see a **default URL** like:

  ```
  https://<appname>.azurewebsites.net
  ```
* Open it to check your app is running (you’ll see a default Azure welcome page if you haven’t deployed code yet).

---

### **11. Deploy Your Code**

You can deploy using:

* **Azure Portal → Deployment Center** (connect GitHub/DevOps).
* **VS Code with Azure Tools extension** → right-click → Deploy to Azure.
* **Azure CLI** → `az webapp up -n <appname> -g <resourcegroup>`.
* **Zip Deploy** (upload `.zip` file via portal).
* **FTP / Local Git**.

---

✅ Now your web app / API is live!

---

⚡ Do you want me to also give you **step-by-step using Azure CLI** (instead of portal), so you can automate App Service creation in scripts?
