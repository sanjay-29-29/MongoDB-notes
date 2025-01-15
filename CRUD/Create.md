## [db.collection.insertOne()](https://www.mongodb.com/docs/manual/reference/method/db.collection.insertOne/)

```javascript
db.collection.insertOne(
    <document>,
    {
      writeConcern: <document>
    }
)
```

- If the collection does not exist, then the [`insertOne()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.insertOne/#mongodb-method-db.collection.insertOne) method creates the collection.
- If the document does not specify an [_id](https://www.mongodb.com/docs/manual/reference/glossary/#std-term-_id) field, then [`mongod`](https://www.mongodb.com/docs/manual/reference/program/mongod/#mongodb-binary-bin.mongod) will add the `_id` field and assign a unique [`ObjectId()`](https://www.mongodb.com/docs/manual/reference/method/ObjectId/#mongodb-method-ObjectId) for the document before inserting. Most drivers create an ObjectId and insert the `_id` field, but the [`mongod`](https://www.mongodb.com/docs/manual/reference/program/mongod/#mongodb-binary-bin.mongod) will create and populate the `_id` if the driver or application does not. If the document contains an `_id` field, the `_id` value must be unique within the collection to avoid duplicate key error.
- - -

## [db.collection.insertMany()](https://www.mongodb.com/docs/manual/reference/method/db.collection.insertMany/)

```javascript
db.collection.insertMany(
   [ <document 1> , <document 2>, ... ],
   {
      writeConcern: <document>,
      ordered: <boolean>
   }
)
```

- By default, documents are inserted in the order they are provided.
- If `ordered` is set to `true` and an insert fails, the server does not continue inserting records.
- If `ordered` is set to `false` and an insert fails, the server continues inserting records.