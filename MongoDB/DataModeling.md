- One to one
- One to many
- Many to many

Data that is accessed together should be stored together.

The two primary ways of modeling data relationships in MongoDB are embedding and referencing.

### Embedding:

Used when you have one-to-many or many-to-many relationships in the data that’s being stored.

- Avoids application joins
- Provides better performance for read operations
- Allows developers to update related data in a single write operation

**Warning:**

- Embedding data into a single document can create large documents
- Large documents have to be read into memory in full, which can result in a slow application performance for your end user
- Continuously adding data without limit creates unbounded documents
- Unbounded documents may exceed the BSON document threshold of 16 MB

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
- Bloated documents
- Unnecessary indexes
- Queries without indexes
- Data that’s accessed together, but stored in different collections