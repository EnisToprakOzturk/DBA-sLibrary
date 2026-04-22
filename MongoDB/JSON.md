- JavaScript Object Notation
- Simple associative containers
- A string key is mapped to a value
- Human and machine-readable
- Comparatively simple to implement support for other languages
- JavaScript became the default language of client-side web development
- JSON shows up in many different cases:
    - APIs
    - Configuration files
    - Log messages
    - Database storage

# JSON Examples

- Simple Key - Value pairs

```json
{
"name": "MongoDB",
"type": "Document-based NoSQL Databaase"
}
```
---
- Key - Array value pairs

```json
{
"name": "MongoDB",
"tags": ["Document", "NoSQL",
 "Database", "Leaf"]
}
```
---
- Key - Embedded value pair

```json
{ 
"name": {
	"first": "John",
	"last": "Adams"
	}
}
```
---
- Key - Array of Embedded value pairs

```json
{
"awards": [
		{
				"award": "W.W. McDowell Award",
				"year": 1967,
				"by": "IEEE Computer Society"
		}, {
				"award": "Draper Prize",
				"year": 1993,
				"by": "National Academy of Engineering"
		}
	]
}
```

---

```json
{
	"_id": 1,
	"name": {"first": "John", "last": "Backus"},
	"contribs": ["Fortran", "ALGOL","FP"],
	"awards": [
		{
				"award": "W.W. McDowell Award",
				"year": 1967,
				"by": "IEEE Computer Society"
		}, {
				"award": "Draper Prize",
				"year": 1993,
				"by": "National Academy of Engineering"
		}
	]
}
```