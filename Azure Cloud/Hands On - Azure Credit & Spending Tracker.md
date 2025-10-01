# 🟦 Azure Credit & Spending Tracker

This guide helps you **check your remaining Azure credits** and **track how much you have spent**. Useful for both individual accounts and enterprise subscriptions.

---

## 🔹 Prerequisites

Before starting, make sure you have:

* 🧑‍💻 An **Azure account** (Free Trial, Pay-As-You-Go, or Enterprise)
* 🌐 Access to the **Azure Portal**
* 🔑 Optionally, **Azure CLI** installed for command-line checking

---

## 🔹 Method 1: Check Credits via Azure Portal

### Step 1: Sign in to Azure Portal

* Go to [https://portal.azure.com](https://portal.azure.com)
* Use your **Microsoft Account credentials**

### Step 2: Navigate to Subscription

* Click on **☰ Menu → Subscriptions**
* Select the **subscription** you want to check
  
<img width="426" height="329" alt="image" src="https://github.com/user-attachments/assets/0fa58889-69f2-4f43-b9b8-0b4d5833a92a" />

<img width="869" height="210" alt="image" src="https://github.com/user-attachments/assets/191a5321-5352-4a41-9d50-6dffbce44b14" />

<img width="1889" height="348" alt="image" src="https://github.com/user-attachments/assets/3b9d1bdb-1dbe-4090-b8ae-ea60c2fe4888" />

### Step 3: View Credit Balance

* Look for **💰 “Balance”** or **💳 “Credits”** section
* You can see:

  * **Remaining Credit**
  * **Total Amount Spent**
  * **Expiry Date** (if using trial credits)

<img width="1397" height="817" alt="image" src="https://github.com/user-attachments/assets/9ea5da50-85c9-4b0a-8e0b-f6088fb1f073" />

### Step 4: Download Usage Report (Optional)

* Click **Usage + charges → Download**
* Export CSV to see **detailed resource-wise spend**

---

## 🔹 Method 2: Check Credits via Azure Cost Management

### Step 1: Navigate to Cost Management

* Go to **☰ Menu → Cost Management + Billing → Cost Management**

### Step 2: Check Overview

* **📊 Overview** shows:

  * **Current spending**
  * **Budget alerts**
  * **Forecast for the month**

### Step 3: Analyze by Service

* Click **Cost Analysis → Group by Service**
* Understand which services **consume most credits**

---

## 🔹 Method 3: Check Credits via Azure CLI

> Requires [Azure CLI installed](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

### Step 1: Login to Azure CLI

```bash
az login
```

> A browser window will open to authenticate

### Step 2: List Subscriptions

```bash
az account list --output table
```

* Shows all subscriptions and their **IDs** and **status**

### Step 3: Check Usage

```bash
az consumption usage list --subscription <SUBSCRIPTION_ID> --output table
```

* Displays **services used** and **amount spent**
* Optional filters:

```bash
az consumption usage list --start-date 2025-10-01 --end-date 2025-10-31 --output table
```

> Replace dates as required to check monthly usage

---

## 🔹 Step 4: Set Up Budget Alerts (Recommended)

1. Go to **Cost Management → Budgets → + Add**
2. Set **budget limit** (e.g., $200 credit/month)
3. Add **email alerts** for 50%, 75%, 90% usage

---

## 🔹 Tips & Tricks

* 🔍 Regularly monitor **Cost Analysis** to prevent overspending
* 📈 Use **Forecast** to plan your cloud usage
* 🔔 Enable **alerts** to avoid credit expiration without notice

---

## 🟢 Summary

| Method          | What You See                     | Tools Needed |
| --------------- | -------------------------------- | ------------ |
| Portal          | Credit balance, spent amount     | Browser      |
| Cost Management | Detailed usage, charts, forecast | Browser      |
| Azure CLI       | Resource-level usage             | Azure CLI    |

---

💡 **Pro Tip:** For automated monitoring, combine **Azure CLI + scripts** to fetch credit balance daily and alert via email/Teams.
