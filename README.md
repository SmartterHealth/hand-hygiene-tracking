# hand-hygiene-tracking
Hand hygiene tracking sample solution.

# Database

ClinicalOutcomes

A user [COUser] has been granted db_datareader and db_datawriter roles. This user can be used when connecting the Hand Hygiene PowerApp to the database. 

**NOTE:** The password is *ClinicalOutcomes2018*. It is recommended you change the password **immediately** after setup by logging into your SQL Server with an account that has appropriate permissions and executing the following command:

```
use master
alter login [COUser] with password = "your_new_password"
```
