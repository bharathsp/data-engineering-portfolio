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

<img width="582" height="931" alt="image" src="https://github.com/user-attachments/assets/e998ea81-0c70-4fc5-a0d3-5172a102c0ba" />

<img width="593" height="728" alt="image" src="https://github.com/user-attachments/assets/9cebca6b-dd63-4840-8631-0c40ab2b61b5" />

---

### **5. Configure Deployment (Optional)**

* Tab: **Deployment**
* You can link a **GitHub repo**, **Azure Repos**, or use **manual deployment**.
* If you skip now, you can configure CI/CD later.

<img width="511" height="933" alt="image" src="https://github.com/user-attachments/assets/3cf6ee9f-54f6-42d8-8613-a41b4b592cd1" />

---

### **6. Networking (Optional)**

* Choose whether the app should have **public access** or integrate with a **VNet**.
* By default → leave as public.

<img width="512" height="551" alt="image" src="https://github.com/user-attachments/assets/28fa1992-6b22-4206-8dcb-7ca2444e9e31" />

---

### **7. Monitoring**

* Enable **Application Insights** (recommended) to collect logs, performance data, and failures.
* Choose region for Insights (ideally same as App Service region).

<img width="530" height="935" alt="image" src="https://github.com/user-attachments/assets/d3f79725-452a-4b08-aeea-be736105d77e" />

---

### **8. Tags (Optional)**

* Add tags for cost tracking (e.g., `Dept=Finance`, `Project=WebApp`).

<img width="585" height="361" alt="image" src="https://github.com/user-attachments/assets/7ab46238-2716-46d7-8c08-81667a352e66" />

---

### **9. Review + Create**

* Azure will validate your settings.
* Click **Create**.
* Deployment takes a few minutes.

<img width="527" height="944" alt="image" src="https://github.com/user-attachments/assets/b4672202-ecf1-4be0-8ece-8c0808e0026e" />

<img width="582" height="598" alt="image" src="https://github.com/user-attachments/assets/9a40119c-161f-46e9-8de5-196593d5b17a" />

---

### **10. Access Your App**

* Once deployment finishes, go to **App Services → Your App → Overview**.
* You’ll see a **default URL** like:

  ```
  https://<appname>.azurewebsites.net
  ```
* Open it to check your app is running (you’ll see a default Azure welcome page if you haven’t deployed code yet).

<img width="586" height="911" alt="image" src="https://github.com/user-attachments/assets/6f9e0796-5054-44f7-a69f-c77c460c70c9" />

<img width="544" height="1044" alt="image" src="https://github.com/user-attachments/assets/07fbd316-bf66-4de5-85a7-c3d4f4ddf88f" />

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
