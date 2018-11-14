# Hand Hygiene Tracking Starter Solution

Hand hygiene tracking starter solution.

# Database

ClinicalOutcomes

A user [COUser] has been granted *db_datareader* and *db_datawriter* roles. While this enables simple setup and documentation, it is not necessarily the most secure. It is recommended that you examine the database security and tune security and permissions to your organitions specific needs.

**NOTE:** The password is *ClinicalOutcomes2018*. It is recommended you change the password **immediately** after setup by logging into your SQL Server with an account that has appropriate permissions and executing the following command:

```
use master
alter login [COUser] with password = "your_new_password"
```


# Misc.

## Debugging

Pass a query string parameter named *debug* with a value of *1* to the PowerApp to enable a debug info screen. This screen can be used to clear/reload the cached reference data.

![alt-text][easter-egg-1_1]


[easter-egg-1_1]: https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_1.png "Debug button"
[easter-egg-1_2]: https://github.com/SmartterHealth/hand-hygiene-tracking/blob/master/images/easter-egg1_2.png "Debug screen"
