# BSON
- “Binary JSON”
- Encodes type and length information
- BSON has more datatypes compared to JSON
- Allows comparisons and calculations to happen directly on data
- MongoDB stores data in BSON format internally and over the network
- Anything in JSON can be stored in MongoDB and retrieved

# BSON  Data Types

### Double

- Stores floating point values

```json
{
	"number": 10.21
}
```

### String

- BSON strings are UTF-8

```json
{
	"name": "MongoDB"
}
```

### Integer

- Stores numeric  values

```json
{
	"counter": 1234321
}
```

### Min-key, Max-key

- Compares the value against the lowest and highest BSON element

```json
{"$minKey": 1}
OR
{"maxKey": 1}
```

### Array

- Stores arrays or list or multiple values into one key

```json
{
	"tags": ["hello", 10]
}
```

### Timestamp

- Updates timestamp when document added or modified

```json
{
	"ts": Timestamp(1412180887, 1)
}
```

### Boolean

- Stores a boolean (true/false) value
- 

```json
{
	"American_citizenship": false
}
```

### Date

- Stores the current date time in UNIX time format

```json
{
	"$date": "2019-08-11T17:54:14:692Z"
}
```

### ObjectId

- Stores the document’s ID

```json
{
	"$oid": "5d5489574cd879bvc97"
}
```

### JavaScript

- Used to store JavaScript code into the document

### Regular expression

- Used to store regular expressions

### Binary Data

- Used to store binary data

### Null

- Used to store a Null value

### Object

- Used for Embedded document