Database &rarr; Properties &rarr; Options &rarr; Recovery Model

# Simple

~~~sql
USE [master]
GO
ALTER DATABASE [AdventureWorks2022] 
SET RECOVERY SIMPLE WITH NO_WAIT
GO
~~~

# Full

~~~sql
USE [master]
GO
ALTER DATABASE [AdventureWorks2022] 
SET RECOVERY FULL WITH NO_WAIT
GO
~~~

# Bulk Logged

~~~sql
USE [master]
GO
ALTER DATABASE [AdventureWorks2022] 
SET RECOVERY BULK_LOGGED WITH NO_WAIT
GO
~~~~

# Point in Time Recovery

* Last full backup
* Last differential backup
* All of the transaction log backup thereafter

# NORECOVERY vs RECOVERY

~~~sql 
USE [master]
GO

RESTORE DATABASE [DB_Name] WITH RECOVERY
~~~

# Transact-SQL Syntax for restoring to LSN

~~~sql
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO
~~~
LSN &rarr; log  sequence number

~~~sql
select database_name, 
	case [type]
		when 'D' then 'Full'
		when 'I' then 'Differential'
		when 'L' then 'Transaction Log'
	end as BackupType,
	first_lsn, last_lsn,
	database_backup_lsn, checkpoint_lsn
from msdb.dbo.backupset
where database_name = '<db_name>'
~~~
