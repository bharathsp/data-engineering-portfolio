**Cost Alerts** in Azure help you **stay notified when your spending crosses certain thresholds** (like 80% of your budget). These alerts are created through **Budgets** in Azure Cost Management.

---

## ⚡ Steps to Set a Cost Alert in Azure

1. **Go to Cost Management**

   * In the [Azure Portal](https://portal.azure.com), search for **Cost Management**.
     <img width="902" height="150" alt="image" src="https://github.com/user-attachments/assets/98973cd2-fa22-4957-a98e-f60bf0e05e31" />

   * Select **Monitoring → Budgets**.
     <img width="872" height="451" alt="image" src="https://github.com/user-attachments/assets/536bf2b4-06ee-4333-afab-b22075ccc5d6" />


2. **Create a Budget**

   * Click **+ Add** (to create a new budget).
     <img width="413" height="134" alt="image" src="https://github.com/user-attachments/assets/c0f6b4e4-d1bb-4945-9e43-9d7762ae3ddf" />

   * Select the **scope** (Billing account, Subscription, or Resource Group).
     <img width="507" height="525" alt="image" src="https://github.com/user-attachments/assets/a07c2a22-dc36-4c01-aa03-9e781305b30b" />

   * Enter a **budget name** and choose the **reset period** (monthly, quarterly, annually).
   * Enter the **budget amount** (e.g., ₹10,000 or $500). <br>
     <img width="449" height="354" alt="image" src="https://github.com/user-attachments/assets/65f4c2c3-ed4e-44d4-a049-20220958b60f" />


3. **Set Alerts**

   * Under **Alert conditions**, you can define thresholds.
   * Example:

     * **80% of budget** → Send alert email.
     * **100% of budget** → Another alert.
   * You can set multiple alert rules. <br>
     <img width="515" height="636" alt="image" src="https://github.com/user-attachments/assets/d09b4fd6-8e9a-4155-bd80-467f61f1b4f5" />


4. **Choose Recipients**

   * Add **Azure AD users, groups, or service principals** who should receive the alert.
   * By default, you can send alerts via **email**. <br>
     <img width="513" height="838" alt="image" src="https://github.com/user-attachments/assets/8727f4e3-eef9-4976-9bec-c31a0493e76b" />


5. **Review & Create**

   * Click on create.
     <img width="1919" height="507" alt="image" src="https://github.com/user-attachments/assets/10d7e007-a9e2-4531-b27a-e89a582746c0" />
     
   * Azure will now automatically monitor spend and send alerts when thresholds are reached.
     <img width="1919" height="795" alt="image" src="https://github.com/user-attachments/assets/425a0813-3e5e-482d-b613-bbbbda452c60" />



---

## 📩 What Happens Next

* When costs exceed your set threshold, Azure sends an **email notification** to the specified recipients.
* Alerts don’t stop resources automatically — they only notify you.
* If you need automation (e.g., shutting down VMs), you can connect alerts to **Azure Action Groups** + **Logic Apps** for custom workflows.

---

✅ **Example use case:**

* Budget: $200/month
* Alert 1: 50% ($100) → email to team lead
* Alert 2: 80% ($160) → email to manager
* Alert 3: 100% ($200) → email + trigger automation (stop non-critical VMs)
