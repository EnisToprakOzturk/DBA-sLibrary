# MongoDB Shell

- An interactive JavaScript interface to MongoDB
- Used for:
    - add new data
    - query the existing data
    - update the existing data
    - remove the data
    - perform administrative operations
- Separate Installation
- Can be installed on the same location as the server binary

```bash
mongosh --port <portnumber> 
--host <hostname | ip adress>

mongosh --username <username> 
--password <password>
--authenticationDatabase admin 
```

# Installing and Connecting to the MongoDB Shell

The following code demonstrates how to install and use `mongosh` in a Linux environment.

1. Update `apt` and install `gnupg`. Then add the MongoDB public GPG key to the system.

```sql
apt update
apt install <code>gnupg</code>
wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | sudo apt-key add -
```

1. Create a list file for MongoDB.

```sql
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu
focal/mongodb-org/6.0 multiverse" | sudo tee
/etc/apt/sources.list.d/mongodb-org-6.0.list
```

1. Update `apt` and install `mongosh`.

```
apt update
apt install -y mongodb-mongosh
```

1. Check that `mongosh` is installed.

```sql
mongosh --version
```

1. Exit `mongosh`.

```
exit
```


# Accessing Mongo Shell Help

### Command-line help

```bash
./mongosh --help
```

### Shell help

```sql
help
```

### Database help

```sql
db.help()
```

### Collection help

```sql
db.createCollection("testCollection")
db.testCollection.help()
```

### Cursor help

```sql
db.testCollection.find().
```
 
---

## Edit Commands in an External Editor

To edit a function or command in an external text editor, like Vim or nano, while using `mongosh`, use the `edit` command. To use this command, you must first set the `config.editor` value in `mongosh`. To do so, use the `config.set()` method:

```sql
config.set("editor", "vim")
```

Once the editor is set, you can then use `edit` to modify a new or existing command. For example, to edit the `giveMeADate` function, you would run the following code:

```
edit giveMeADate
```
