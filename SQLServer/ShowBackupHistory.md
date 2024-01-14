# Database Backups for all databases For Previous Week

~~~sql
--------------------------------------------------------------------------------- 
--Database Backups for all databases For Previous Week 
--------------------------------------------------------------------------------- 
SELECT 
   CONVERT(CHAR(100), SERVERPROPERTY('Servername')) AS Server, 
   msdb.dbo.backupset.database_name, 
   msdb.dbo.backupset.recovery_model,
   msdb.dbo.backupset.backup_start_date, 
   msdb.dbo.backupset.backup_finish_date, 
   CASE msdb..backupset.type 
      WHEN 'D' THEN 'Database'  
      WHEN 'I' THEN 'Incremental'  
      WHEN 'L' THEN 'Log'
      END AS backup_type, 
   msdb.dbo.backupset.backup_size,  
   msdb.dbo.backupmediafamily.physical_device_name,
   msdb.dbo.backupmediafamily.family_sequence_number,
   msdb.dbo.backupset.name AS backupset_name, 
   msdb.dbo.backupset.description, 
   msdb.dbo.backupset.expiration_date, 
   msdb.dbo.backupmediafamily.logical_device_name
FROM 
   msdb.dbo.backupmediafamily 
   INNER JOIN msdb.dbo.backupset ON msdb.dbo.backupmediafamily.media_set_id = msdb.dbo.backupset.media_set_id 
WHERE 
   (CONVERT(datetime, msdb.dbo.backupset.backup_start_date, 102) >= GETDATE() - 7) 
ORDER BY  
   msdb.dbo.backupset.backup_finish_date desc
~~~