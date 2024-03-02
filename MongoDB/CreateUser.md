```sql
db.createUser( 
    { user: "superadmin", 
    pwd: "supersecret", 
    roles: 
        [{role: "root", 
        db: "admin"}] } )
```