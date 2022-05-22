# Kata 3 Solutions
## Liberate 


The document pattern is a "Set".

Output _id + single item pairs:

```javascript
db.brands.aggregate([
  {
    "$unwind": "$colors"
  }
])
```


Add index to each item into a field named `originalOffset`

```javascript
db.brands.aggregate([
  {
    "$unwind": {
      "path": "$colors",
      includeArrayIndex: "originalOffset"
    }
  }
])
```


Suppress output of documents which had no colors

```javascript

db.brands.aggregate([
  {
    "$unwind": {
      "path": "$colors",
      "preserveNullAndEmptyArrays": true
    }
  }
])
```
