Title: Shrinking database log file to specific size
Published: 05/27/2017
Category: Microsof tMS SQL
Tags: Microsoft MS SQL
---

In MS SQL server there may be a chance to get “The log file for database ‘DatabaseName’ is full.”

One of the way to fix this problem is backup the database and shrinking database log file to specific size. You can use Right click on database and choose Task -> Shrink -> Database in Microsoft SQL Server Management Studio to shrink the database. You can shrink the database file using Task -> Shrink -> File to shrink the Log or Data file. Instead of this, you can use the SQL script to shrink the log file.

The syntax to shrink the database log file is as follows.

```SQL
USE DatabaseName;
GO
-- Truncate the log by changing the database recovery model to SIMPLE.
ALTER DATABASE DatabaseName
SET RECOVERY SIMPLE;
GO
-- Shrink the truncated log file to (specify size here) 1 MB.
DBCC SHRINKFILE (DatabaseName_log, 1);
GO
-- Reset the database recovery model.
ALTER DATABASE DatabaseName
SET RECOVERY FULL;
GO
```

In this syntax DatabaseName is name of your database.

DatabaseName_log is logical name of your database. (Not physical file name of the database log file)

You can get this log file name using the following way.

Open the MS SQL Server Management Studio.

Select the database property by right click the database in Object explorer.

Click the Files page (below to the General).

Now you can see the logical name for the database in the Database files grid under Logical Name column.

For Example

```SQL
USE AdventureWorks;
GO
ALTER DATABASE AdventureWorks
SET RECOVERY SIMPLE;
GO
-- Shrink the truncated log file to 1 MB.
DBCC SHRINKFILE (AdventureWorks_Log, 1);
GO
ALTER DATABASE AdventureWorks
SET RECOVERY FULL;
GO
```
Here the logical name of the database is “AdventureWorks_Log”