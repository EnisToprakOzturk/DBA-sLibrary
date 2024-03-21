### Show Cluster Nodes

~~~sql
select * from sys.dm_os_cluster_nodes
~~~

### Show OS and DB Version

~~~sql
select @@version
~~~

### Show Service and Server Name

~~~sql
select @@servicename, @@servername
~~~

### Size of Database Files

~~~sql
SELECT DB_NAME(database_id) AS database_name, 
    type_desc, 
    name AS FileName, 
    size/128.0 AS CurrentSizeMB,
    physical_name
FROM sys.master_files
order by CurrentSizeMB desc
~~~

### Show Disk Usage

~~~sql
SELECT DISTINCT dovs.logical_volume_name AS LogicalName,
	dovs.volume_mount_point AS Drive,
	CONVERT(INT,dovs.available_bytes/1048576.0) AS FreeSpaceInMB
	,CONVERT(INT,dovs.total_bytes/1048576.0) AS TotalSpaceInMB
	,CONVERT(INT,dovs.total_bytes/1048576.0) - CONVERT(INT,dovs.available_bytes/1048576.0) AS UsedSpaceInMB
	FROM sys.master_files mf
	CROSS APPLY sys.dm_os_volume_stats(mf.database_id, mf.FILE_ID) dovs
~~~