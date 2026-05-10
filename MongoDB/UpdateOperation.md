# Update Operation

 Modifies existing documents in a collection
- Targets a single collection
- Atomic write operations on the single documents level
- You can specify criteria, or filters
- You cannot update the value of the _id field

```sql
db.<collection_name>.updateMany(
	{ age: { $lt: 18 } },
	{ $set: { status: "reject" } }
)
```
age < 18 , set their status as reject