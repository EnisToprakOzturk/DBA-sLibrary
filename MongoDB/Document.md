- Data records as BSON documents
- Composed of field-value pairs
- Field can be any of the BSON data types
- Value can be other documents, arrays, and arrays of documents
- It is similar to JSON document
- Can have more than one field with the same name
- The maximum BSON document size is 16 megabytes
- _id is primary key, auto-generated

```json
var mydoc = {
	_id: ObjectId("32894898fhdf87dff868g1"),
	name: {first: "Alan", last: "Turing"},
	birth: new Date('Jun 21, 1912'),
	death: new Date('Jun 07, 1954'),
	contribs: ["Turing machine", 
		"Turing test", "Turingery"],
	views: NumberLong(1250000)
}
```