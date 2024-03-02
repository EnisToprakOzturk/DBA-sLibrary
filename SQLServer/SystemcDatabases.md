### master

Master database is a system database that stores configuration settings, metadata, and information about all other databases on the server instance.

### model

The model database is a system database used as a template to create new user databases, providing default settings and objects for any new database created on the server instance.

### msdb

The msdb database is a system database that stores information related to SQL Server Agent, including job schedules, alerts, operators, and maintenance plans, as well as other system metadata and historical data.

### tempdb

The tempdb database is a system database used to store temporary objects such as temporary tables, variables, and query results for the duration of a session or a transaction.

### resource database

The resource database is a read-only system database that stores system objects and metadata required for the SQL Server instance to function, serving as a template for system database upgrades.

**Note:** The resource database is a hidden system database that is not directly accessible or visible in SQL Server Management Studio (SSMS) or through typical database management commands. It is stored in the SQL Server installation directory, typically located in the "\Program Files\Microsoft SQL Server\MSSQL{InstanceName}\Binn" directory, and it consists of a set of files named "mssqlsystemresource.mdf" and "mssqlsystemresource.ldf". However, direct access or manipulation of the resource database is not supported or recommended by Microsoft, as it is a critical component of the SQL Server instance's internal functionality.