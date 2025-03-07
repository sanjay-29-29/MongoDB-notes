## Structure of an Aggregation Pipeline

``` javascript
db.collection.aggregate([
    {
        $stage1: {
            { expression1 },
            { expression2 }...
        },
        $stage2: {
            { expression1 }...
        }
    }
])
```

- - - 
# `$match`

The `$match` stage filters for documents that match specified conditions. Here's the code for `$match`:

```javascript
{
  $match: {
     "field_name": "value"
  }
}
```

- - -
## `$group`

The `$group` stage groups documents by a group key.

``` javascript
{
  $group:
    {
      _id: <expression>, // Group key
      <field>: { <accumulator> : <expression> }
    }
 }
```

- - --
## `$match` and `$group` in an Aggregation Pipeline

The following aggregation pipeline finds the documents with a field named "state" that matches a value "CA" and then groups those documents by the group key "$city" and shows the total number of zip codes in the state of California.

``` javascript
db.zips.aggregate([
{   
   $match: { 
      state: "CA"
    }
},
{
   $group: {
      _id: "$city",
      totalZips: { $count : { } }
   }
}
])
```

- - -
# Using `$sort` and `$limit` Stages in a MongoDB Aggregation Pipeline

Review the following sections, which show the code for the `$sort` and `$limit` aggregation stages.

## `$sort`

The `$sort` stage sorts all input documents and returns them to the pipeline in sorted order. We use 1 to represent ascending order, and -1 to represent descending order.

```javascript
{
    $sort: {
        "field_name": 1
    }
}
```


- - -

## `$limit`

The `$limit` stage returns only a specified number of records.

```javascript
{
  $limit: 5
}
```

  - - -

## `$sort` and `$limit` in an Aggregation Pipeline

The following aggregation pipeline sorts the documents in descending order, so the documents with the greatest `pop` value appear first, and limits the output to only the first five documents after sorting.

```javascript
db.zips.aggregate([
{
  $sort: {
    pop: -1
  }
},
{
  $limit:  5
}
])
```

- - -
## [`$lookup`](https://www.mongodb.com/docs/manual/reference/operator/aggregation/lookup/#mongodb-pipeline-pipe.-lookup)

- Performs a left outer join to a collection in the _same_ database to filter in documents from the "joined" collection for processing. The [`$lookup`](https://www.mongodb.com/docs/manual/reference/operator/aggregation/lookup/#mongodb-pipeline-pipe.-lookup) stage adds a new array field to each input document. The new array field contains the matching documents from the "joined" collection. The [`$lookup`](https://www.mongodb.com/docs/manual/reference/operator/aggregation/lookup/#mongodb-pipeline-pipe.-lookup) stage passes these reshaped documents to the next stage.

```javascript
{
   $lookup:
     {
       from: <collection to join>,
       localField: <field from the input documents>,
       foreignField: <field from the documents of the "from" collection>,
       as: <output array field>
     }
}
```

- - -
## [ `$out`](https://www.mongodb.com/docs/manual/reference/operator/aggregation/out/)

- Takes the documents returned by the aggregation pipeline and writes them to a specified collection. You can specify the output database.

- The `$out` stage must be _the last stage_ in the pipeline. The `$out` operator lets the aggregation framework return result sets of any size.

``` javascript
{ $out: "<output-collection>" } // Output collection is in the same database
{ $out: { db: "<output-db>", coll: "<output-collection>" } }
```