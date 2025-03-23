# Order-Tracking-Event-Driven-Data-Ingestion

The Client is a Logistics company. The Client sends order details files daily to ADLS source. Load data from csv source files in ADLS Source folder to Delta table (staging table) where it is overwritten. The Source files are moved to an Archive folder. The data should be processed such that if 'NA' value in status column should be left blank or with no value.
The data from staging delta table is then sent to target delta table where the operation is upsert. The notebook is linked to github account. The source files in ADLS gen2 should be deleted at 11 pm daily. Also, create a databricks workflow to start the tasks whenever a new file is loaded into the source folder in ADLS.


Steps for App Registration in Azure
1.	Go to Azure Portal → Azure Active Directory → App registrations
2.	Click New registration, give it a name, and register it.
3.	Copy the Application (Client) ID and Directory (Tenant) ID
4.	Go to Certificates & secrets → New client secret → Copy the secret value.
5.	Go to Azure Storage Account → Access Control (IAM) → Add role assignment
   --> Select Storage Blob Data Contributor
   -->	Assign it to the registered App


Steps to Configure the Workflow
1.	Go to Databricks Workspace
2.	Click Workflows → Create Job
3.	Job Name: Process ADLS Data
4.	Task Type: Select Notebook
5.	Notebook Path: Select the notebook containing all tasks
6.	Cluster: Choose an existing cluster or create a new one
7.	Trigger Options:
o	For automatic execution: Set Trigger on File Arrival

