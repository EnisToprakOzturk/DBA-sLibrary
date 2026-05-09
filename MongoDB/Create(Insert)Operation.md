# Create (Insert) Operation

- Add new documents to the collection
- It creates the collection
- Targets single collection
- Automic write operations on the single document level
- Unique _id filed, which acts as primary key
- Auto-creates _id field if not present

```sql
db.<collection>.insertOne(
	{
		name: "enis",
		age: 28,
		status: "pending"
	}
)
```