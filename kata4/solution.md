# Kata 4 Solutions
## Isolate 


The document pattern is a "Flat". All field values are reachable using dotted notation without concern for their order.

Filter on nested field:

```javascript
db.customers.aggregate([
  {
    "$match": {
      "address.state": "NH"
    }
  }
])

```


Sort by nested field:

```javascript
db.customers.aggregate([
  {
    "$sort": {
      "address.unit": 1
    }
  }
])
```
