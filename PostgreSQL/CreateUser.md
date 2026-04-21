# Users In Postgresql

* Database users and operating system users are completely separate
* User name should be unique and should not start with “pg_”
* Postgres super user is created default on installation of postgresql
* Postgres user has all the privileges with grant option
* Only super users or users with create role privilege can create user
* Database users are global across the cluster

```sql
createuser --help
create user <user_name> password 'password';
create user <user_name> password 'password' VALID UNTIL '2005-01-01';
createuser -U postgres --interactive
```

```sql
CREATE USER name [ [ WITH ] option [ ... ] ]
where option can be:
      SYSID uid 
    | CREATEDB | NOCREATEDB
    | CREATEUSER | NOCREATEUSER
    | IN GROUP groupname [, ...]
    | [ ENCRYPTED | UNENCRYPTED ] PASSWORD 'password'
    | VALID UNTIL 'abstime'
```

### Revoke connect database privilege 

```sql
revoke connect on database <user_name> from <db_name>; 
```