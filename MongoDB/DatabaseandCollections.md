# Collections

- Documents store
- Collections == RDBMS Tables
- Creates collection when you write data into the collection

```json
{
  "_id": {
    "$oid": "56e9b39b732b6122f877fbd5"
  },
  "airline": {
    "id": 2916,
    "name": "Intersky",
    "alias": "3L",
    "iata": "ISK"
  },
  "src_airport": "EBA",
  "dst_airport": "ACH",
  "codeshare": "",
  "stops": 0,
  "airplane": "DH3"
}
```

# Databases

- Holds one or more collections
- Databases == RDBMS Databases
- Creates the database when you first store data for that database

<p align="center">
  <img src="/Images/MDBDatabase.png">
</p>