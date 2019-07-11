![SmartterHealth](https://i.imgur.com/YAmuJGYm.jpg?1 "SmartterHealth")

# Hand Hygiene Tracking Starter Solution

This is the hand hygiene tracking starter solution referenced in the Microsoft Health & LIfe Sciences blog post  [The "Power" Platform in Healthcare: Monitoring Hand Hygiene Adherence](https://techcommunity.microsoft.com/t5/Healthcare-and-Life-Sciences/The-quot-Power-quot-Platform-in-Healthcare-Monitoring-Hand/ba-p/345136) .

# Deployment

Deployment of the Hand Hygiene app assumes that you have some experience with managing [Microsoft SQL Server](https://docs.microsoft.com/en-us/sql/lp/sql-server/install-sql-and-services?view=sql-server-2017) , [PowerApps](https://docs.microsoft.com/en-us/powerapps/index) , and SQL connections. If you are not familiar with these procedures, please see the [guided learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps&resource_type=learning%20path)  for PowerApps before attempting to deploy the Hand Hygiene starter solution.

## Deploy the ClinicalOutcomes Database

The easiest way to get the SQL Server database up and running is to deploy to SQL Azure. You can deploy to on-premises, but you will need to install and configure a gateway. To install the *ClinicalOutcomes* database, perform the following steps.

1) Download *ClinicalOutcomes.bacpac* to your local machine from [here][bacpac].
2) Upload the *ClinicalOutcomes.bacpac* file to [Azure Blob Storage.][azblob].
3) Import the *ClinicalOutcomes.bacpac* blob into [Azure SQL Server][azbacpac].

#### IMPORTANT! Database Security

A database login named *COUser* has already been created in the ClinialOutcomes database and has been granted *db_datareader* and *db_datawriter* roles. While this enables simple setup and documentation, it is not necessarily the most *secure*. It is ***recommended*** that you examine the database security and tune security and permissions to your organitions specific needs.

**NOTE:** The password is *ClinicalOutcomes2018*. It is recommended you change the password ***immediately*** after setup by logging into your SQL Server with an account that has appropriate permissions and executing the following command (You can perform this from  [Azure](https://azure.microsoft.com/en-us/blog/t-sql-query-editor-in-browser-azure-portal/) or [SQL Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017).

```
use master
alter login [COUser] with password = "your_new_password"
```

## Deploy the Hand Hygiene Tracking PowerApp

### Create the SQL Server Connection

You will need to create a database connection to the ClinicalOutcomes database in order for the Hand Hygiene PowerApp to work properly. Follow the steps provided in the article *[Connect to SQL Server from PowerApps](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/connections/connection-azure-sqldatabase#build-an-app-from-scratch)*  to create a new SQL database connection in PowerApps. 

### Import the PowerApp Package.

Once you have created the database connection to the ClinicalOutcomes database, you are ready to import the Hand Hygiene PowerApp into Microsoft PowerApps. Follow the steps in the article *[Importing an app package](https://powerapps.microsoft.com/en-us/blog/powerapps-packaging/)* to import the Hand Hygiene PowerApps package into your Office 365 environment.

## Deploy the Power BI Report

[TBD]

# Misc.

## Easter Egg

Pass a query string parameter named *debug* with a value of *1* to the PowerApp to enable a debug info screen. This screen can be used to clear/reload the cached reference data.

**Debug Button**

![Debug Button](https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_1.png) 

**Debug Screen**

![Debug Screen](https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_2.png) 


[easter-egg-1_1]: https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_1.png "Debug button"
[easter-egg-1_2]: https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_2.png "Debug screen"
[bacpac]: db/ClinicalOutcomes.bacpac
[azblob]: https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/move-data-to-azure-blob-using-azure-storage-explorer
[azbacpac]: https://docs.microsoft.com/en-us/azure/sql-database/sql-database-import#import-from-a-bacpac-file-using-azure-portal
****