# [db.collection.updateOne()](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/)

```javascript
db.collection.updateOne(
   <filter>,
   <update>,
   {
     upsert: <boolean>,
     writeConcern: <document>,
     collation: <document>,
     arrayFilters: [ <filterdocument1>, ... ],
     hint:  <document|string>,
     let: <document>,
     sort: <document>
   }
)
```

- finds the first document that matches the [filter](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/#std-label-update-one-filter) and applies the specified [update](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/#std-label-update-one-update) modifications.
- upsert : Creates a new document if no documents match the `filter`.
- - -
##  [db.collection.updateMany()](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateMany/#db.collection.updatemany-- "Permalink to this heading")

```javascript
db.collection.updateMany(
   <filter>,
   <update>,
   {
     upsert: <boolean>,
     writeConcern: <document>,
     collation: <document>,
     arrayFilters: [ <filterdocument1>, ... ],
     hint:  <document|string>,
     let: <document>
   }
)
```

- `updateMany()` finds all documents in the collection that match the `filter` and applies modifications specified by the `update` parameter.
- `updateMany()` modifies each document individually
- - - 
# [db.collection.findAndModify()](https://www.mongodb.com/docs/manual/reference/command/findAndModify/)

```javascript
db.runCommand(
   {
     findAndModify: <collection-name>,
     query: <document>,
     sort: <document>,
     remove: <boolean>,
     update: <document or aggregation pipeline>,
     new: <boolean>,
     fields: <document>,
     upsert: <boolean>,
     bypassDocumentValidation: <boolean>,
     writeConcern: <document>,
     maxTimeMS: <integer>,
     collation: <document>,
     arrayFilters: <array>,
     hint: <document|string>,
     comment: <any>,
     let: <document> // Added in MongoDB 5.0
   }
)
```

- The [`findAndModify`](https://www.mongodb.com/docs/manual/reference/command/findAndModify/#mongodb-dbcommand-dbcmd.findAndModify) command updates and returns a single document. By default, the returned document does not include the modifications made on the update. To return the document with the modifications made on the update, use the `new` option.
