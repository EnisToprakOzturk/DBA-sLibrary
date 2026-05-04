## ACID Transactions

A group of database operations that will completed as a unit or not at all

ACID (Atomicity - Consistency - Isolation - Durability)

### Multi-document ACID Transactions

- MongoDB “locks” resources involved in a transaction
- Incurs performance cost and affects latency
- Use multi-document transactions as a precise tool

## Using a Transaction

Here is a recap of the code that's used to complete a multi-document transaction:

```jsx
const session = db.getMongo().startSession()

session.startTransaction()

const account = session.getDatabase('< add database name here>').getCollection('<add collection name here>')

//Add database operations like .updateOne() here

session.commitTransaction()
```

## Aborting a Transaction

If you find yourself in a scenario that requires you to roll back database operations before a transaction is completed, you can abort the transaction. Doing so will roll back the database to its original state, before the transaction was initiated.

## Aborting a Transaction

Here is a recap of the code that's used to cancel a transaction before it completes:

```jsx
const session = db.getMongo().startSession()

session.startTransaction()

const account = session.getDatabase('< add database name here>').getCollection('<add collection name here>')

//Add database operations like .updateOne() here

session.abortTransaction()
```