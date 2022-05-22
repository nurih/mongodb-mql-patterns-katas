# Kata 2 Solutions
## Bunch Up 


The document pattern is "Flat".

Average score across all students all subjects

```javascript
db.scores.aggregate([
  {
    "$group": {
      "_id": "SOME_TITLE_HERE",
      "overallAverage": {
        "$avg": "$score"
      }
    }
  }
])
```


Maximum score by subject

```javascript
db.scores.aggregate([
  {
    "$group": {
      "_id": "$subject",
      "maximum score for this subject": {
        "$max": "$score"
      }
    }
  }
])
```


Count of scores (documents) broken down by name+subject

```javascript
db.scores.aggregate([
  {
    "$group": {
      "_id": {
        name: "$name",
        subject: "$subject"
      },
      "n": {
        "$sum": 1
      }
    }
  }
])```
