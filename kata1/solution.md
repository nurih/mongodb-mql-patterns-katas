# Kata 1 Solutions
## Pass or Not 


The document pattern is "Flat".

All documents where city is "Jackson":

```javascript
db.peeps.aggregate([
  {
    "$match": {
      "city": "Jackson"
    }
  }
])
```


All documents by city name ascending, then by person's name descending:

```javascript
db.peeps.aggregate([
  {
    "$sort": {
      "city": 1,
      "_id": -1
    }
  }
])
```


Second document only from the results above.

```javascript
db.peeps.aggregate([
  {
    "$sort": {
      "city": 1,
      "_id": -1
    }
  },
  {
    "$skip": 1
  },
  {
    $limit: 1
  }
])
```
