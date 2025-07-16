# azure-sql-db-sample-deployment
# 🗄️ Azure SQL Database Deployment — Logical Server, Sample Data & VM Connectivity

## Overview  
This project demonstrates how to deploy an **Azure SQL Database** under a logical SQL Server with secure authentication, networking configuration, and sample data provisioning. It includes access validation through both the Azure Portal and **Azure Data Studio**, plus firewall integration with a linked Windows-based virtual machine.

---

## 🛠️ Technologies Used
- **Azure SQL Database** – Cloud-hosted relational DB  
- **Azure SQL Server** – Logical container (`glsqlserver02`)  
- **AdventureWorksLT Sample Data** – Loaded for query testing  
- **Resource Group** – `GL-SQL-RG` for organized resource management  
- **Virtual Machine** – Windows 10 Pro VM (`GL-SQL-VM`)  
- **Firewall Rules** – Configured public IP access  
- **Azure Data Studio** – GUI-based SQL query execution

---

## 🚀 Deployment Workflow

### Step 1: Create Resource Group  
Deployed `GL-SQL-RG` in East US to organize SQL and VM resources.

### Step 2: Provision Azure SQL Server  
- Server name: `glsqlserver02`  
- Location: East US  
- Authentication: SQL authentication (`mbadmin`)

### Step 3: Deploy SQL Database  
- Database name: `SampleDB`  
- Tier: General Purpose (Serverless)  
- Loaded sample schema: `AdventureWorksLT`

### Step 4: Create Virtual Machine  
- VM name: `GL-SQL-VM`  
- OS: Windows 10 Pro  
- Zone: East US  
- Credentials: `gladmin / Password1Password2`

### Step 5: Configure Firewall Rule  
- Rule name: `AzureVMAccess`  
- IP range: `40.76.251.110`  
- Enabled access from the VM to SQL Server

### Step 6: Test Access  
- Connected to `SampleDB` using Azure Data Studio  
- Ran: `SELECT * FROM [SalesLT].[Customer]`  
- Verified dataset retrieval and server responsiveness

---

## ✅ Outcomes  
- Successfully deployed and queried Azure SQL Database with sample data  
- Integrated VM access via firewall rule and public IP  
- Used GUI tools to confirm network access and data interaction  
- Gained experience in Azure networking, DB provisioning, and authentication flow  


