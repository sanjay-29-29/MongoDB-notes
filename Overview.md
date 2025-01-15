###  1.1 Identify the set of value types MongoDB BSON supports.

[BSON Types](https://www.mongodb.com/docs/manual/reference/bson-types/#bson-types "Permalink to this heading")

| Type               | Number | Alias        | Notes       |
| ------------------ | ------ | ------------ | ----------- |
| Double             | 1      | "double"     |             |
| String             | 2      | "string"     |             |
| Object             | 3      | "object"     |             |
| Array              | 4      | "array"      |             |
| Binary data        | 5      | "binData"    |             |
| Undefined          | 6      | "undefined"  | Deprecated. |
| ObjectId           | 7      | "objectId"   |             |
| Boolean            | 8      | "bool"       |             |
| Date               | 9      | "date"       |             |
| Null               | 10     | "null"       |             |
| Regular Expression | 11     | "regex"      |             |
| DBPointer          | 12     | "dbPointer"  | Deprecated. |
| JavaScript         | 13     | "javascript" |             |
| Symbol             | 14     | "symbol"     | Deprecated. |
| 32-bit integer     | 16     | "int"        |             |
| Timestamp          | 17     | "timestamp"  |             |
| 64-bit integer     | 18     | "long"       |             |
| Decimal128         | 19     | "decimal"    |             |
| Min key            | -1     | "minKey"     |             |
| Max key            | 127    | "maxKey"     |             |

### Given three documents that are of different shape, identify which can co-exist in the same collection.

- A collection can have documents with different schema.
- It  _id field must be different for each document inserted into the collection.
- Rest of fields can be similar to other documents in the collection.

