```sql
SELECT  
  [restore_date]
      ,[destination_database_name]
      ,[user_name]
      ,[backup_set_id]
      ,[restore_type]
      ,[replace]
      ,[recovery]
      ,[restart]
  FROM [msdb].[dbo].[restorehistory]
```

**restore_date:** It shows the database restoration date.
**destination_database_name:** We can get the destination database name using this column.
**user_name:** it gives user name that performed the restoration for that particular database.
**backup_set_id:** We can join this column with backupset table to get information about the backup file.
**restore_type:** We can use this column to know the kind of database restoration performed on particular database.
* D - Database
* I - Incremental
* L - Log
* V - Verifyonly
**replace:** once we execute a database restore command, we set this option to replace the existing destination database.
* 1 - Specified
* 0 - Not specified
**recovery:** In the database restore query, we also specify the Recovery and Norecovery option to bring the database open for users or not.
* 1 - Recovery
* 0 - No recovery
**restart:** It shows ****whether the restore operation specified the RESTART option or not.
* 1 - Specified
* 0 - Not specified

```sql
SELECT
 rh.destination_database_name AS [Database],
  CASE WHEN rh.restore_type = 'D' THEN 'Database'
  WHEN rh.restore_type = 'F' THEN 'File'
   WHEN rh.restore_type = 'I' THEN 'Differential'
  WHEN rh.restore_type = 'L' THEN 'Log'
    ELSE rh.restore_type 
 END AS [Restore Type],
 rh.restore_date AS [Restore Date],
 bmf.physical_device_name AS [Source], 
 rf.destination_phys_name AS [Restore File],
  rh.user_name AS [Restored By]
FROM msdb.dbo.restorehistory rh
 INNER JOIN msdb.dbo.backupset bs ON rh.backup_set_id = bs.backup_set_id
 INNER JOIN msdb.dbo.restorefile rf ON rh.restore_history_id = rf.restore_history_id
 INNER JOIN msdb.dbo.backupmediafamily bmf ON bmf.media_set_id = bs.media_set_id
ORDER BY rh.restore_history_id DESC
```