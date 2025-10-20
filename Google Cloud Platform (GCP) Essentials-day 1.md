## **🧭 What is a GCP Project?**

**A GCP (Google Cloud Platform) Project is the main container for all your cloud resources (like VMs, databases, storage, APIs, etc.).**  
 **Everything you do in GCP happens inside a project.**

## **🧱 Key Concepts of a GCP Project**

| Concept | Description | Example |
| ----- | ----- | ----- |
| **Project ID** | **Unique identifier for the project (auto-generated or custom).** | **my-sample-project-12345** |
| **Project Name** | **Friendly display name (can change anytime).** | **Student Management System** |
| **Project Number** | **Internal numeric ID (fixed).** | **987654321098** |
| **Billing Account** | **Links your project to payment (for paid services).** | **Linked to your credit card or organization account.** |
| **APIs & Services** | **Each GCP feature (like Compute Engine, BigQuery) must be enabled per project.** | **Enable Compute Engine API for VMs.** |
| **IAM (Identity & Access Management)** | **Controls who can access or modify resources.** | **Admin, Developer, Viewer roles.** |
| **Service Accounts** | **Special accounts for apps/services to access resources securely.** | **Used by a web app to read from Cloud Storage.** |

## **⚙️ How GCP Projects Work**

1. **Create a project → It becomes your workspace.**

2. **Enable services you need (e.g., Storage, Compute Engine).**

3. **Assign permissions to users or service accounts.**

4. **Add resources (VMs, databases, APIs, etc.).**

5. **Monitor & manage costs via billing and budgets.**  
   

## **🌍 Uses of GCP Projects**

| Use Case | GCP Services Commonly Used |
| ----- | ----- |
| **Web Hosting / Apps** | **Compute Engine, App Engine, Cloud Run, Firebase Hosting** |
| **Data Storage & Backup** | **Cloud Storage, Bigtable, Filestore** |
| **Machine Learning & AI** | **Vertex AI, TensorFlow, AI APIs (Vision, Speech, NLP)** |
| **Data Analytics** | **BigQuery, Dataflow, Dataproc** |
| **Networking / Cloud Infrastructure** | **VPC, Cloud DNS, Load Balancing, Cloud Armor** |
| **DevOps & CI/CD** | **Cloud Build, Artifact Registry, Cloud Source Repositories** |
| **IoT Applications** | **IoT Core, Pub/Sub, Cloud Functions** |
| **Serverless Development** | **Cloud Functions, Cloud Run, Firestore** |

## **🔐 Benefits of Using GCP Projects**

**✅ Separation of environments — keep dev, test, and prod separate**  
 **✅ Better access control — assign IAM roles per project**  
 **✅ Cost tracking — see cost per project or team**  
 **✅ Security & Compliance — audit logs, policies, and encryption**  
 **✅ Scalability — easily add more services/resources when needed**

## **🧩 Example Structure (Real Use Case)**

**Project: “Student Management System”**

* **Compute Engine: hosts the backend API**

* **Cloud SQL: stores student data**

* **Cloud Storage: stores student photos and PDFs**

* **IAM Roles:**

  * **Admin: full control**

  * **Teacher: read/write student data**

  * **Viewer: read-only access**

* **Billing: tracks monthly cost**

* **Monitoring: Cloud Monitoring & Logs Explorer**

**🧠 Best Practices**

1. **Use separate projects for Dev, Test, and Production.**

2. **Assign least privilege IAM roles (avoid “Owner” for all).**

3. **Set up budgets and alerts to monitor spending.**

4. **Enable required APIs only (for security).**

5. **Use labels to organize resources by team or purpose.**

**![][image1]**  
**🎯 Purpose of a Budget in GCP**

A **budget** helps you **monitor and control your spending** on GCP resources.  
 It allows you to:

* Set **spending limits** (monthly, quarterly, or yearly)

* Get **email alerts** when spending crosses thresholds

* Avoid **unexpected high bills**  
  
## 
## 

## **⚙️ Steps to Create a Budget in GCP**

### **🧩 Step 1: Open the Google Cloud Console**

* Go to **console.cloud.google.com**

* Sign in with your Google account.

### **📁 Step 2: Select Your Project**

* On the top navigation bar, choose the **project** you want to set a budget for.

* (Each project has its own billing account and cost tracking.)

### **💳 Step 3: Go to Billing Section**

* In the left sidebar, click **☰ Menu → Billing**

* Choose the **Billing Account** linked to your project.

### **📊 Step 4: Create a Budget**

* Under **Billing**, select **Budgets & alerts**

* Click **➕ CREATE BUDGET**

### **🧾 Step 5: Define Budget Scope**

Choose what the budget applies to:

* **Entire billing account** (all projects)

* **A specific project**

* **Specific services or labels**

➡ Example:  
 You can budget **only for Compute Engine** or for the **entire project**.

### **💰 Step 6: Set Budget Amount**

Choose your **budget type**:

1. **Fixed amount** — You define a specific amount (e.g., ₹1,000/month)

2. **Last month’s spend** — Automatically uses your previous month’s total.

3. **Specified percentage** — e.g., 110% of last month’s spend.

### **📩 Step 7: Set Budget Alerts**

Add **alert thresholds** (percentages of your budget).  
 You can get email alerts when spending crosses those limits.

Example:

* 50% alert → Early warning

* 90% alert → Almost full

* 100% alert → Budget reached

📬 Alerts are sent to:

* Billing account administrators

* Users you add manually (emails)

### **📈 Step 8: (Optional) Connect to Pub/Sub**

If you want **automated responses** (like shutting down VMs when budget exceeds),  
 you can publish alerts to a **Pub/Sub topic**, and trigger **Cloud Functions**.

### **✅ Step 9: Review and Create**

* Review all settings

* Click **Create Budget**

Your budget is now active\! 🎉  
 You’ll start receiving alerts based on your usage.

## **🧠 Example:**

| Item | Value |
| ----- | ----- |
| Project | Student Management System |
| Budget Type | Fixed |
| Amount | ₹2,000 per month |
| Alerts | 50%, 90%, 100% |
| Alert Recipient | admin@example.com |

## **💡 Tips**

* Create **separate budgets** for different projects or teams.

* Review **billing reports** regularly to identify cost spikes.

* Use **Labels** (like env=dev, team=network) to track spending by environment.

## **☁️ What is Cloud IAM?**

**Cloud IAM (Identity and Access Management)** is a **security service** in Google Cloud Platform (GCP) that lets you **control who (identity)** has **what access (role/permission)** to **which resource**.

💡 **Simple Meaning:**  
 IAM \= *Who can do what on which resource.*

## **🔑 Purpose of Cloud IAM**

* Manage **user access** to GCP resources.

* Assign **roles and permissions** securely.

* Maintain **least privilege** (give only what’s necessary).

* Ensure **audit and compliance** with organization rules.

## 

## 

## **🧩 Main Components of IAM**

| Component | Description | Example |
| ----- | ----- | ----- |
| **Identity** | The entity that requests access (user, group, service account, etc.) | user:mukesh@gmail.com |
| **Resource** | The GCP object you want to protect | VM instance, Storage bucket |
| **Role** | Collection of permissions | roles/viewer, roles/editor |
| **Policy** | Set of bindings (who gets what role on which resource) | IAM policy for a project |
| **Binding** | Connects members (identities) to roles | Mukesh → Viewer role on Project |

## **🧠 How IAM Works (In Simple Terms)**

1. **User or service** tries to perform an action (e.g., start a VM).

2. GCP checks the **IAM policy** on that resource.

3. If the user’s **role** has that permission → ✅ access granted.

4. If not → ❌ access denied.

## **👥 Types of Identities**

| Identity Type | Description | Example |
| ----- | ----- | ----- |
| **Google Account** | Personal user account | user@gmail.com |
| **Service Account** | For apps or VMs to access resources securely | myapp@appspot.gserviceaccount.com |
| **Google Group** | Group of users (for easier management) | dev-team@company.com |
| **Cloud Identity / Workspace** | Organizational user accounts | user@company.com |
| **AllAuthenticatedUsers** | Any signed-in user | (used in public apps) |

## 

## **🧾 Types of IAM Roles**

| Type | Description | Example |
| ----- | ----- | ----- |
| **Primitive Roles** | Basic roles applied at project level | Viewer, Editor, Owner |
| **Predefined Roles** | Specific roles for GCP services | roles/compute.admin, roles/storage.objectViewer |
| **Custom Roles** | User-defined roles with selected permissions | roles/custom.networkMonitor |

### **🔹 Primitive Roles**

| Role | Access Level | Permissions |
| ----- | ----- | ----- |
| Viewer | Read-only | Can view resources only |
| Editor | Modify resources | Can read/write but not manage IAM |
| Owner | Full control | Can manage everything including IAM |

### **🔹 Predefined Roles (Examples)**

| Service | Role | Description |
| ----- | ----- | ----- |
| Compute Engine | roles/compute.admin | Full access to VM instances |
| Cloud Storage | roles/storage.objectAdmin | Manage bucket objects |
| BigQuery | roles/bigquery.dataViewer | View datasets and tables |

### **🔹 Custom Roles**

* Created when predefined roles give too many or too few permissions.

* You choose only the permissions needed.

* Useful for **least privilege principle**.

## 

## **🏗️ IAM Hierarchy (Inheritance)**

IAM policies apply **hierarchically**:

**Organization → Folder → Project → Resource**

➡ Permissions at higher levels are **inherited** by lower levels.

Example:  
 If a user has “Viewer” role at the **Project** level,  
 they automatically get read access to **all resources** inside that project.

## **🔐 Best Practices**

✅ Follow **least privilege principle** — only necessary access.  
 ✅ Use **groups** instead of adding many users individually.  
 ✅ Use **service accounts** for automation.  
 ✅ Regularly **review IAM policies**.  
 ✅ Avoid using **Owner** role broadly.  
 ✅ Enable **Audit Logs** to monitor access.

## **📊 Real-World Example**

**Project:** student-management-system

* admin@school.com → **Owner**

* teacher@school.com → **Editor**

* viewer@school.com → **Viewer**

* app-service@project.iam.gserviceaccount.com → **Service Account User**

## **🧩 Command-Line Example (gcloud)**

\# View IAM policy for a project  
gcloud projects get-iam-policy my-project-id

\# Add a new user with viewer role  
gcloud projects add-iam-policy-binding my-project-id \\  
  \--member="user:mukesh@gmail.com" \\  
  \--role="roles/viewer"

## **📊 What is a Quota in GCP?**

A **quota** in Google Cloud Platform is a **limit** that Google sets on how much of a particular resource or service you can use.

💡 **Simple meaning:**  
 A **quota** prevents overuse of GCP resources — both to protect you from unexpected bills and to protect Google’s systems from abuse.

## **🎯 Purpose of Quotas**

1. **Prevent accidental overuse** of resources (e.g., too many VMs).

2. **Ensure fair resource sharing** among all users.

3. **Control cost and resource usage** for each project.

4. **Maintain system stability and performance.**

## **🧩 Types of Quotas**

| Type | Description | Example |
| ----- | ----- | ----- |
| **Rate Quotas** | Limit how many API requests can be made per second or minute. | Cloud Storage API → 1000 requests/min |
| **Resource Quotas** | Limit the number of resources you can create in a project or region. | 24 CPU cores per region, 50 VMs per project |

## 

## 

## 

## 

## **🏗️ Examples of Common Quotas in GCP**

| GCP Service | Example Quota | Description |
| ----- | ----- | ----- |
| **Compute Engine** | CPUs per region | Limit how many virtual CPUs you can use. |
| **Cloud Storage** | Buckets per project | Maximum number of buckets allowed. |
| **BigQuery** | API requests per day | Controls how many queries you can run daily. |
| **Cloud Functions** | Function invocations per 100 seconds | Prevents overuse of serverless functions. |
| **Pub/Sub** | Messages per minute | Limits publishing and subscribing rates. |

---

## **🧠 Quota vs Limit**

| Feature | Quota | Limit |
| ----- | ----- | ----- |
| **Definition** | Adjustable usage restriction | Fixed maximum system restriction |
| **Can it be increased?** | ✅ Yes (request via console) | ❌ No |
| **Example** | 24 CPUs per region | Max 256 CPUs per VM (cannot exceed) |

## 

## **⚙️ How to View Quotas**

### **🖥️ From Cloud Console**

1. Go to **console.cloud.google.com/iam-admin/quotas**

2. Select your **project**.

3. Use filters to see:

   * By **service** (e.g., Compute Engine)

   * By **region**

4. You’ll see columns:

   * Metric (type of quota)

   * Limit (maximum allowed)

   * Usage (current usage)

   * Limit type (regional/global)

## **📈 How to Increase Quota**

If you hit a quota limit, you can **request an increase**:

### **🪜 Steps:**

1. Go to **IAM & Admin → Quotas** in Cloud Console.

2. Select the quota(s) you want to increase.

3. Click **Edit Quotas → Request Quota Increase**.

4. Fill out:

   * **New limit** you want

   * **Region**

   * **Business reason**

5. Google Support reviews and approves (usually within 1–2 days).

💡 *Note:* You need **Billing enabled** and **Owner/Editor role** to request increases.

## **🔐 Best Practices for Managing Quotas**

✅ Monitor quotas regularly in the **Cloud Console**.  
 ✅ Set up **alerts** in Cloud Monitoring for nearing limits.  
 ✅ Request **increases early** for upcoming workloads.  
 ✅ Use **labels** to track which projects use more resources.  
 ✅ Automate checks via the **Service Usage API**.

## **🧾 Command-Line Examples (gcloud)**

\# List all quotas for a project

gcloud compute regions describe asia-south1

\# Check quota usage for a specific service

gcloud services quotas list \--service=compute.googleapis.com

\# Request quota increase (link provided by console)

## **🧩 Real-Life Example**

**Project:** “Web Hosting Project”

* **Compute Engine CPUs (per region):** 24 used out of 24 → 🚫 cannot create new VMs.

* **Solution:** Request quota increase to 48 CPUs in the same region.

## 

## 

## 

## 

## 

## **📘 Summary Table**

| Feature | Description |
| ----- | ----- |
| **Quota Purpose** | Limit usage, prevent overuse, control cost |
| **Quota Types** | Rate-based & Resource-based |
| **Set By** | Google Cloud |
| **Adjustable?** | Yes, via Quota Increase Request |
| **Location** | Console → IAM & Admin → Quotas |
| **Common Example** | CPUs per region, API calls per minute |

[image1]: <data:image/png;base64,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>