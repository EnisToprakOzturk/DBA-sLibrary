- PostgreSQL stores the metadata information about the database and cluster in the schema ‘pg_catalog’
- PostgreSQL manages system catalogs by itself

| Name  | Description |
| --- | --- |
| pg_database | Stores general database info |
| pg_stat_database | Contains stat information of database |
| pg_tablespace | Contains Tablespace information |
| pg_operator | Contains all operator information |
| pg_available_extensions | List all available extensions |

```sql
select * from pg_database;
select * from pg_stat_database;
select * from pg_tablespace;
select * from pg_operator;
select * from pg_available_extensions;
select * from pg_shadow;
select * from pg_timezone_names;
select * from pg_locks;
select * from pg_tables;
select * from pg_settings where name='max_connections';
select * from pg_settings where name='port';
select * from pg_indexes;
select * from pg_views;
select current_schema();
select current_user();
select current_database();
select current_setting('max_parallel_workers');
select current_setting('max_connections');
select pg_postmaster_start_time();
select now() as current;
```