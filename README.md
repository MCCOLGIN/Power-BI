# Power-BI
Created 20260624
Issue: How to setup Power BI with Project Server and produce Power BI reports.

Here’s a clear, step‑by‑step guide on how to install Power BI, connect it to Project Server (On‑Prem or Project Online), and run reports. I’ll keep it practical for someone in Program Planning & Scheduling.

1. Install Power BI Desktop
Power BI Desktop is free and is required to build reports.
Option A – Microsoft Store (Recommended):

Open the Microsoft Store.
Search Power BI Desktop.
Click Get/Install.

Option B – Direct Download (.msi installer):

Go to https://powerbi.microsoft.com/desktop
Download the 64‑bit installer.
Run the installer and complete setup.

Once installed, launch Power BI Desktop.

2. Determine Your Project Server Environment
Before connecting Power BI, identify which you’re using:
• Project Online (cloud, part of Microsoft 365)
• Project Server On‑Prem (hosted internally, usually connected to SQL Server)
The connection method is different for each.
If you’re not sure, I can help you identify based on your URL.

3A. Connect Power BI to Project Online (OData Feed)
This is the most common for enterprise program scheduling teams.


Open Power BI Desktop.


Click Get Data.


Select OData Feed.


Enter the Project Online OData URL:
https://.sharepoint.com/sites/pwa/_api/ProjectData

https://msproject.vgh.local/sites/PBO/Projects.aspx 

Click OK.


When prompted, sign in with your Microsoft 365 credentials.


Select the datasets you want, such as:

Projects
Tasks
Assignments
Resources
ProjectBaselines
TimesheetLineActualDataSet



Click Load.


This gives you a complete set of tables you can model and report on.

3B. Connect Power BI to Project Server On‑Prem (SQL Database)
If your organization uses Project Server installed on‑prem:


Get the SQL Server name and database from IT:

Usually named ProjectWebApp.



In Power BI Desktop, click Get Data.


Choose SQL Server.


Enter:

Server: 
Database: ProjectWebApp (or whatever your PWA DB is called)



Use Import (or DirectQuery if allowed by your IT).


Select tables such as:

MSP_EpmProject
MSP_EpmTask
MSP_EpmAssignment
MSP_EpmResource



Click Load.


Note: Some data may require reporting views (MSP_Epm… tables are normally safe to read).

4. Build Power BI Reports
Now that your data is loaded:

Create visuals using fields like:

Project Name
Start/Finish
% Complete
Baseline Start/Finish
Work / Remaining Work


Useful charts for scheduling:

Milestone dashboards
Baseline variance charts
Resource allocation charts
Slip tracking visual


Use Filters or Slicers for:

Program → Project → WBS
Team or CAM
Time period


Save your report.

If your environment uses Power BI Service:
You can then publish via Home → Publish.

5. Common Project Server + Power BI Issues
Here are some issues program schedulers often hit:
• OData is slow → Use SQL Server if on-premise.
• Relationships not automatically created → You must manually build relationships.
• Date columns come in as text → Change data type to Date.
• Assignment data "duplicates" projects → Create a dimension table for Projects using DISTINCT, then relate properly.
If you want, I can help you build a proper data model for Projects/Tasks/Assignments.

Want me to prepare a starter report for you?
I can build a template that includes:
• Project list
• Task summary
• Baseline variance chart
• Milestone slip report
• Resource over/under allocation visual
Just tell me which system you’re connecting to (Project Online or On‑Prem).
Would you like that?



