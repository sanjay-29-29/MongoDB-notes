MongoDB provides several logical operators that enable combining multiple query conditions. These operators allow you to construct complex queries by specifying conditions that documents must satisfy.

| **Operator** | **Description**                                                                                         |
| ------------ | ------------------------------------------------------------------------------------------------------- |
| `$and`       | Joins query clauses with a logical **AND**; returns documents that match all the specified conditions.  |
| `$or`        | Joins query clauses with a logical **OR**; returns documents that match at least one of the conditions. |
| `$not`       | Inverts the effect of a query expression and returns documents that do **not** match the condition.     |
| `$nor`       | Joins query clauses with a logical **NOR**; returns documents that do not match any of the conditions.  |
- - -
## Examples

### 1. `$and` Example
Find documents where `age` is greater than 18 and `status` is `"active"`.
```javascript
db.collection.find({
  $and: [
    { age: { $gt: 18 } },
    { status: "active" }
  ]
});
```

## 2. `$or` Example
Find documents where `age` is less than 18 or `status` is `"inactive"`.
```javascript
db.collection.find({
  $or: [
    { age: { $lt: 18 } },
    { status: "inactive" }
  ]
});
```

## 3. `$not` Example
Find documents where `age` is **not** greater than 18.
```javascript
db.collection.find({
  age: { $not: { $gt: 18 } }
});
```

# 4. `$nor` Example
Find documents where `age` is neither less than 18 nor `status` is `"inactive"`.
```javascript
db.collection.find({
  $nor: [
    { age: { $lt: 18 } },
    { status: "inactive" }
  ]
});
```