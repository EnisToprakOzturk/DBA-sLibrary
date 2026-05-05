### Restoring a Database

```sql
USE [master]
RESTORE DATABASE [AdventureWorks2022] 
FROM  DISK = N'C:\DBA\AdventureWorks2022.bak' 
WITH  STATS = 5
GO
```
---

```sql
`STATS = 5`
```

Prints a **progress message every 5%** of completion. You'll see output like:

```
5 percent processed.
10 percent processed.
15 percent processed.
...
100 percent processed.
```
