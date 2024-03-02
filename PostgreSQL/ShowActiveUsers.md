```sql 
select usename
from pg_stat_activity 
where state = 'active';
```