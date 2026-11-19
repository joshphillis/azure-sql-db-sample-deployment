azure-sql-db-sample-deployment
🗄️ Azure SQL Database Deployment — Logical Server, Sample Data & VM Connectivity
Overview

This project deploys an Azure SQL Database under a logical SQL server with SQL authentication, server-level firewall rules, and the AdventureWorksLT sample dataset. Access is validated from a Windows virtual machine using Azure Data Studio.

All resource names, logins, and IP addresses below are placeholders. Real credentials and network identifiers have been removed, and the original lab resources have been deleted.

🛠️ Technologies Used
Azure SQL Database: cloud-hosted relational database (General Purpose, Serverless)
Azure SQL logical server: container for the database and its firewall rules
AdventureWorksLT sample data: loaded for query testing
Resource group: one group for all SQL and VM resources
Windows virtual machine: client used to test connectivity
Server-level firewall rule: allows the VM's public IP
Azure Data Studio: GUI-based query execution
🚀 Deployment Workflow

Step 1: Create the resource group

Name: <resource-group>
Region: East US

Step 2: Provision the logical SQL server

Name: <sql-server-name>
Region: East US
Authentication: SQL authentication (<sql-admin-login>)

Step 3: Deploy the database

Name: SampleDB
Tier: General Purpose (Serverless)
Sample schema: AdventureWorksLT

Step 4: Create the client VM

Name: <vm-name>
OS: Windows 10 Pro
Region: East US
Local admin: <vm-admin> with a strong password (not stored in this repo)

Step 5: Configure the firewall rule

Rule name: AzureVMAccess
Start/end IP: <vm-public-ip>
Allows only the VM's public IP to reach the SQL server

Step 6: Test access

Connected to SampleDB from the VM using Azure Data Studio
Ran a validation query:
sql
SELECT TOP (10) * FROM [SalesLT].[Customer];
Confirmed data retrieval and server responsiveness
✅ Outcomes
Deployed and queried an Azure SQL Database loaded with sample data
Restricted server access to a single client IP with a server-level firewall rule
Validated connectivity and data access from a VM with Azure Data Studio
Gained hands-on experience with Azure SQL provisioning, authentication, and network access control
🔒 Production Considerations

This lab used SQL authentication and a public-IP firewall rule for simplicity. In production I would:

Use Microsoft Entra ID authentication and disable SQL logins where possible
Use a private endpoint with public network access disabled, instead of IP-based firewall rules
Store any secrets in Azure Key Vault
Turn on auditing and Microsoft Defender for SQL
