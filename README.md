# 💻 Laptop Request Catalog Item

Here you will find all the document files related to the **Laptop Request Catalog Item** project.

---

## 📅 Document Submission

**NOTE:** All dates mentioned in the PDFs are based on when this GitHub repository was submitted to faculty for review.

---

## 👥 Team Details

Team ID : NM2025TMID08544

Team Size : 4

Team Leader : Varsha R

Team member : Venu K C

Team member : Varun Vikas K

Team member : Nighilkrishna M

---

## 📘 Project Overview

This project focuses on building a dynamic Service Catalog Item in ServiceNow to streamline and automate the process of requesting work laptops within an organization. It transforms the traditional manual and delay-prone workflow into an efficient, user-friendly digital experience that ensures accurate data capture and strong governance during deployment.

This solution was developed under the SmartInternz NME program in partnership with ServiceNow and SmartBridge.

---

## 🎯 Problem Statement

Employees rely on a quick, efficient process to get essential equipment. The previous manual process resulted in **delays, confusion, and inaccurate data capture** due to the lack of dynamic form behavior and clear guidance.

The objective was to create a Catalog Item that provides:
1. **Speed and Efficiency:** A single digital submission point  
2. **User Guidance:** Dynamic fields and clear instructions  
3. **Usability:** A form reset option for better user experience (UX)  
4. **Governance:** All configurations tracked for safe deployment

---

## 🛠️ Implementation Steps

The following outlines the configuration sequence within the ServiceNow instance to deploy this solution:

### Step 1: Governance Setup
- Created and activated a **Local Update Set** named **"Laptop Request"** to capture all configuration changes

### Step 2: Service Catalog Item Creation
- Created the main item: **Laptop Request**  
- Configured under the **Service Catalog** and **Hardware** category

### Step 3: Variables Definition

| Variable Name         | Type              | Technical Name           |
|-----------------------|-------------------|---------------------------|
| Laptop Model          | Single Line Text  | `laptop_model`           |
| Justification         | Multi Line Text   | `justification`          |
| Additional Accessories| Checkbox          | `additional_accessories` |
| Accessories Details   | Multi Line Text   | `accessories_details`    |

### Step 4: Dynamic Behavior Implementation
- Created a **Catalog UI Policy** (*Show Accessories Details*)  
- **Condition:** `additional_accessories` is `true`  
- **Action:** Set `accessories_details` to **Visible: True** and **Mandatory: True**

### Step 5: User Experience Action
- Created a **Client UI Action** named **"Reset Form"**  
- **Table:** `sc_cart`  
- **Script:** Uses `g_form.clearForm()` to clear fields and confirm with an alert

### Step 6: Deployment & Migration
- Marked Update Set as **Complete** and **Exported to XML**  
- Imported, Previewed, and **Committed** in the target instance

---

## 🔐 Instance Access & Policy Note


For security and platform compliance reasons, the **ServiceNow Developer (NM) instance link is not publicly disclosed** within this repository.

As per ServiceNow Developer Program Terms of Use:

> “Developer instances are provided strictly for personal learning and development purposes. Public sharing or exposing instance links may result in suspension or termination of access.”

To maintain responsible platform usage and safeguard configuration integrity, this project adheres to recommended best practices by keeping instance access restricted.

To view the working demonstration, evaluators can access it through the **SmartInternz project workspace** under the **DEMO LINK** section.
The ServiceNow instance link has been uploaded there as a document and is available exclusively for authorized review.
