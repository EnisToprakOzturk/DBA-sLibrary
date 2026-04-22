- One to one
- One to many
- Many to many

Data that is accessed together should be stored together.

The tow primary ways of modeling data relationships in MongoDB are embedding and referencing.

### Embedding:

Used when you have one-to-many or many-to-many relationships in the data thath’s being stored.

- Aavoids application joins
- Provides better perormance for read operations
- Allows developers to update related data in a single write operation

**Warning:**

- Embedding data into a single document can create large documents
- Large documnets have to be read into memory in full, which can result in a slow application performance for your end user
- Continuosly adding data without limit creates unbounded documents
- Unbounded documnets may exceed the BSON documnet threshold of 16 MB

| Embedding | Referencing |
| --- | --- |
| Single query to retrieve data | No duplication |
| Single operation to update/delete data | Smaller documents |
| Data duplication | Need to join data from multiple documents |
| Large documents |  |

## Scaling a Data Model

**Avoid:**

- More than the document size limit of 16 MB
- Poor query performance
- Poor write performance
- Too much memory being used

### Common schema anti-patterns:

- Massive arrays
- Massive number of collections
- Bloated documnets
- Unnecessary indexes
- Queries without indexes
- Data that’s accessed together, but stored in different collections