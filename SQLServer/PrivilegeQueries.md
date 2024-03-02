### Show Logins in Default DB

~~~sql
select * from sys.server_principals;
~~~

### Show DB and Its Owner

~~~sql
SELECT name, suser_sname(owner_sid) AS DBOwner FROM sys.databases
~~~

### Show Users

~~~sql
SELECT name, createdate, accdate
FROM master..syslogins;
~~~

### Give privileges on database for stored procedures 

```sql
USE <DBname>
GO
GRANT EXECUTE, ALTER,  VIEW DEFINITION TO <user>
```