# [db.collection.deleteOne()](https://www.mongodb.com/docs/manual/reference/method/db.collection.deleteOne/)

```javascript
db.collection.deleteOne(
    <filter>,
    {
      writeConcern: <document>,
      collation: <document>,
      hint: <document|string>
    }
)
```

- [`db.collection.deleteOne()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.deleteOne/#mongodb-method-db.collection.deleteOne) deletes the first document that matches the filter. Use a field that is part of a [unique index](https://www.mongodb.com/docs/manual/reference/glossary/#std-term-unique-index) such as `_id` for precise deletions.
- - -

# [db.collection.deleteMany()](https://www.mongodb.com/docs/manual/reference/method/db.collection.deleteMany/)

```javascript
db.collection.deleteMany(
   <filter>,
   {
      writeConcern: <document>,
      collation: <document>
   }
)
```

- Removes all documents that match the `filter` from a collection.