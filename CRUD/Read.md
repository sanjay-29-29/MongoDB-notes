# [db.collection.find()](https://www.mongodb.com/docs/manual/reference/method/db.collection.find/)

```javascript
db.collection.find( <query>, <projection>, <options> )
```

- Selects documents in a collection or view and returns a [cursor](https://www.mongodb.com/docs/manual/reference/glossary/#std-term-cursor) to the selected documents.
- without any query find() returns a cursor with the contents of whole collection.
- by default find() returns 20 elements.
- The `_id` field is included in the returned documents by default unless you explicitly specify `_id: 0` in the projection to suppress the field.
- - -

# [db.collection.findOne()](https://www.mongodb.com/docs/manual/reference/method/db.collection.findOne/)

```javascript
db.collection.findOne( <query>, <projection>, <options> )
```

- Returns one document that satisfies the specified query criteria on the collection or [view.](https://www.mongodb.com/docs/manual/core/views/#std-label-views-landing-page)
- Returns the first document if no query is specified.
- The `_id` field is included in the returned documents by default unless you explicitly specify `_id: 0` in the projection to suppress the field.