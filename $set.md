## [link](https://www.mongodb.com/docs/manual/reference/operator/update/set/)

```javascript
{ $set: { <field1>: <value1>, ... } }
```

- The [`$set`](https://www.mongodb.com/docs/manual/reference/operator/update/set/#mongodb-update-up.-set) operator replaces the value of a field with the specified value.
#### Example
```javascript
db.products.updateOne(
   { _id: 100 },
   { $set:
      {
        quantity: 500,
        details: { model: "2600", make: "Fashionaires" },
        tags: [ "coats", "outerwear", "clothing" ]
      }
   }
)
```