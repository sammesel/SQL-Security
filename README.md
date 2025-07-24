# SQL-Security

This is a solution to implement SQL Server security mechanisms to protect data

The implementation is structured using the following features:

## Dynamic Data Masking (DDM)
use DDM to obfuscate PII or PHI data. This will prevent data abuse, i.e. someone with access to the data to see its full content. For example a Customer Service clerk can see only the last 4 digits of a credit card number, or the just the initial 2 digits from customer's last name<br>
If this end user (customer service clerk) gains access to tools like SSMS or any other data extraction tool, all masked columns will be exported with masking<br>

## Row Level Security

## Auditing

## Server Roles, Database Roles, and Custom Roles

This solution **prioritized** finding options using **built-in permissions**, as these are easy to implement and backward compatible with future SQL Server versions

## Ledger



  It is recommended to work first with the contents on the AUDITING folder, and then use the contents on the other folders as needed

  **NOTE**: the database used is a copy of the AdventureWorks sample database<br>
  You can download a copy of the AdventureWorks database from [here](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2019.bak)<br>
  The examples are based on the [AdventureWorks2019](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2019.bak) version - but any version should work with minimal adjustments<br>

## NOTES: 

###  1. All scripts display the **login name** to be used for that script at the very top.<br>
#### line 2 on the image below shows to use **sa**.
![Login Information](images/Username-Password-to-use.png)
<br>
<ul>
<li>Execute the Query to display the username to make sure you are using the correct persona</li>
<li>For scripts that switch between MASTER and the SQLSecurityDemoDB databases:</li>
  <ul>
  <li>After Switching the database, execute the query to display the username again, so you can see how that user is mapped</li>
  <li>When testing these scripts on Azure SQL Database the **USE** command will fail, you need to switch the database manually via SSMS toolbar</li>
  </ul>
</ul>
<br>

### 2. The features demonstrated here work independently.<br>

#### .

## disclaimer

  This Sample Code is provided for illustration only and is not intended to be used in a production environment.<br>
  THIS SAMPLE CODE AND ANY RELATED INFORMATION ARE PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT
  NOT LIMITED TO THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A PARTICULAR 
  PURPOSE.  We grant You a nonexclusive, royalty-free right to use and modify the Sample Code
  and to reproduce and distribute the object code form of the Sample Code, provided that You
  agree:<br> 
    (i) to not use Our name, logo, or trademarks to market Your software product in which the Sample Code is embedded;<br>
    (ii) to include a valid copyright notice on Your software product in which the Sample is embedded;<br>
    and (iii) to indemnify, hold harmless, and defend Us and Our suppliers from and against any claims or lawsuits, including attorneys fees, that arise or result from the use or distribution of the Sample Code.<br> 

## References

The following links are useful resources for your study / SQL security review.
- [Workpshop: SQL Security Ground to Cloud](https://github.com/David-Seis/SecureYourAzureData) by Buck Woody and David Seis<br>
- [Packaging Permissions in Stored Procedures](https://www.sommarskog.se/grantperm.html) by Erland Sommarskog, SQL Server MVP - updated on 2023-06-13.<br>
- [New granular permissions for SQL Server 2022 and Azure SQL to improve adherence with PoLP](https://techcommunity.microsoft.com/t5/sql-server-blog/new-granular-permissions-for-sql-server-2022-and-azure-sql-to/ba-p/3607507) by Andreas Wolter<br>
  
  
