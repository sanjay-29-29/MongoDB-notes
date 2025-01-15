## [link](https://www.mongodb.com/docs/manual/reference/operator/query/elemMatch/)

- The [`$elemMatch`](https://www.mongodb.com/docs/manual/reference/operator/query/elemMatch/#mongodb-query-op.-elemMatch) operator matches documents that contain an array field with at least one element that matches all the specified query criteria.
- Returns the whole document if a match is found in a array field

```javascript
{ <field>: { $elemMatch: { <query1>, <query2>, ... } } }
```

```javascript
Collection:
{ _id: 1, results: [ 82, 85, 88 ] }
{ _id: 2, results: [ 75, 88, 89 ] }

Example:
db.scores.find(
   { results: { $elemMatch: { $gte: 80, $lt: 85 } } }
)

Result:
{ "_id" : 1, "results" : [ 82, 85, 88 ] }
```