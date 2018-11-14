# Hand Hygiene Tracking Starter Solution

Hand hygiene tracking starter solution.


# Deployment

## Deploy the ClinicalOutcomes Database

The easiest way to get the SQL Server database up and running is to deploy to SQL Azure. You can deploy to on-premises, but you will need to install and configure a gateway.

1) Download *ClinicalOutcomes.bacpac* to your local machine from [here][bacpac].
2) Upload the *ClinicalOutcomes.bacpac* file to [Azure Blob Storage.][azblob].
3) Import the *ClinicalOutcomes.bacpac* blob into [Azure SQL Server][azbacpac].

### IMPORTANT! Database Security

A user [COUser] has been granted *db_datareader* and *db_datawriter* roles. While this enables simple setup and documentation, it is not necessarily the most secure. It is recommended that you examine the database security and tune security and permissions to your organitions specific needs.

**NOTE:** The password is *ClinicalOutcomes2018*. It is recommended you change the password **immediately** after setup by logging into your SQL Server with an account that has appropriate permissions and executing the following command:

```
use master
alter login [COUser] with password = "your_new_password"
```

## Install the Hand Hygiene Tracking PowerApp

[TBD]

## Connect the Reports

[TBD]

# Database

ClinicalOutcomes


# Misc.

## Easter Egg

Pass a query string parameter named *debug* with a value of *1* to the PowerApp to enable a debug info screen. This screen can be used to clear/reload the cached reference data.

**Debug Button**
![alt-text][easter-egg-1_1]

**Debug Screen**
![alt-text][easter-egg-1_2]


[easter-egg-1_1]: https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_1.png "Debug button"
[easter-egg-1_2]: https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_2.png "Debug screen"
[bacpac]: db/ClinicalOutcomes.bacpac
[azblob]: https://docs.microsoft.com/en-us/azure/machine-learning/team-data-science-process/move-data-to-azure-blob-using-azure-storage-explorer
[azbacpac]: https://docs.microsoft.com/en-us/azure/sql-database/sql-database-import#import-from-a-bacpac-file-using-azure-portal
