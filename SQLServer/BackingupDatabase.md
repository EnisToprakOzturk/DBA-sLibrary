~~~sql
BACKUP DATABASE [AdventureWorks2022] 
TO  DISK = N'C:\DBA\AdventureWorksBackup2' 
WITH NOFORMAT, NOINIT,  
NAME = N'AdventureWorks2022-Full Database Backup', 
SKIP, NOREWIND, NOUNLOAD,  STATS = 10
GO
~~~
# Different Backup Models

* Full Backup
* Differential Backup
* Transaction Backup
## Transaction Backup

~~~sql
BACKUP LOG [DB_Name] 
TO DISK = N'C:\DBA\AdventureWorksBackup2'
WITH NOFORMAT, NOINIT, 
NAME = N'AdventureWorks-Full Database Backup',
SKIP, NOREWIND, NOUNLOAD, STATS = 10
GO
~~~
## Differential Backup

~~~sql
BACKUP DATABASE [DB_Name]
TO DISK = N'C:\DBA\AdventureWorksBackup2'
WITH DIFFERENTIAL,
NOFORMAT, NOINIT, 
NAME = N'AdventureWorks-Full Database Backup',
SKIP, NOREWIND, NOUNLOAD, STATS = 10
GO
~~~
### To see how much space will backup take:

~~~sql
exec sp_spaceused
exec sp_spaceused '[Person].[Address]'
~~~