- Database cluster is a collection of databases that is managed by a single instance on a server.
- Initdb creates a new PostgreSQL database cluster.
- Creating a database cluster consist of creating the directories which the data is store. We call this the “data directory”.
- We have to first initialize the storage area on the disk before we begin any operation on the database.
- Location of Data Directory:
    - Linux: /var/lib/psql/data (Not mandatory)
    - Windows: C:\Program Files\PostgreSQL\12\data (Not mandatory)

# Initdb Syntax

- We have to be logged in as PostgreSQL user to execute the below commands.
- There are two way to initialize database.

```bash
initdb -D /usr/local/psql/data
pg_ctl -D /usr/psqş/data initdb
```

-D = refers to the data directory location.

-W = we can use this option to force the super user to provide password before initialize db

# Start\Stop Cluster

### Start Cluster Syntax:

```bash
systemctl start postgre@service.15
```

```powershell
pg_ctl -D "C:\Program Files\PostgreSQL\15\data" start
```

### Stop Cluster Syntax:

```bash
systemctl stop postgresql@service.15
```

```powershell
pg_ctl stop -D "C:\Program Files\PostgreSQL\15\data" -m shutdown mode
```

# Type of Shutdowns

- Smart: The server disallows new connections, but lets existing sessions end their work normally. It shuts down only after all of the sessions terminate
- Fast(Default): The server disallows new connections and abort their current transactions and exits gracefully.
- Immediate: Quits/aborts without proper shutdown which lead to recovery on next startup.

# Difference Between Reload and Restart

- When we make changes to server parameters, we need to reload the configuration for them to take effect.
- Reload will just reload the new configurations, without restarting the service
- Few configuration changes in server parameters, Do not get reflected until we restart the service
- Restart gracefully shutdown all activity, relinquishes the resource, close all open files and start again with new configuration.

# Reload\Restart Cluster

### Syntax for Reload of Cluster

```bash
system reload postgresql@service.15
```

```powershell
pg_ctl reload
```

```sql
SELECT pg_reload_conf();
```

### Syntax for Restart of Cluster

```bash
systemctl restart postgre@service.15
```

```powershell
pg_ctl restart
```

