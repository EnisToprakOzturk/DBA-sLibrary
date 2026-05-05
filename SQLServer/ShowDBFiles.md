### Show DB Files 

```sql
select * 
from sys.master_files	
```

### Show Db Files in Spesified Disk
```sql
select * 
from sys.master_files	
where physical_name like 'I:\%'
```