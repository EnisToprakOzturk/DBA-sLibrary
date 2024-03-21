psql — PostgreSQL interactive terminal

# Description

psql is a terminal-based front-end to PostgreSQL. It enables you to type in queries interactively, issue them to PostgreSQL, and see the query results. Alternatively, input can be from a file or from command line arguments. In addition, psql provides a number of meta-commands and various shell-like features to facilitate writing scripts and automating a wide variety of tasks.

```bash
psql
```

# Parameters

---

-d database_name

--dbname = database_name

Specifies the name of the database to connect to. 

---

-f file_name

--file = file_name

Read commands from the file ***`filename`***, rather than standard input.

---

-h host_name

--host = host_name

Specifies the host name of the machine on which the server is running. If the value begins with a slash, it is used as the directory for the Unix-domain socket.

---

-p port_number

--port = port_number

Specifies the TCP port or the local Unix-domain socket file extension on which the server is listening for connections.

---

-U user_name

--username = user_name

Connect to the database as the user ***`username`*** instead of the default. (You must have permission to do so, of course.)

---

-W password

--password password

Force psql to prompt for a password before connecting to a database, even if the password will not be used.

---

-?

--help[=topic]

Show help about psql and exit.

### Example:

~~~sql
psql -h 192.168.1.30 -p 5432 -U postgres -d postgres -W
~~~