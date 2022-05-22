# Kata 5 Solutions
## Shape Up 


The document pattern is a "Flat".

`$project` is a good fit for the _Present_ part of the pattern. It can also be used for the _Gather_ stage in order to simplify expressions that _Assemble_ might require.

Output named fields, suppress the _id.

```javascript
db.scores.aggregate([
  {
    "$project": {
      name: 1,
      score: 1,
      _id: 0
    }
  }
])
```


Generate new field named `boosted` with a value of original `score` plus 5.

```javascript
db.scores.aggregate([
  {
    "$project": {
      score: 1,
      boosted: {
        $add: [
          5,
          "$score"
        ]
      }
    }
  }
])
```

Add a sub-document valued field. Pick components of a data using date operators `$year` and `$month`.

```javascript
db.scores.aggregate([
  {
    "$project": {
      subject: 1,
      "year_and_month": {
        y: {
          $year: "$dt"
        },
        m: {
          $month: "$dt"
        }
      }
    }
  }
])
```
