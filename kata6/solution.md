# Kata 6 Solution
## Combined


The document pattern is "Set"

The operators can be aligned to the pipeline pattern like so:

Pipeline Pattern Part   | MQL Stage
---                     |---
Gather                  |{$match: {colors: "blue"}},
Gather                  |{$unwind: "$colors"},
Assemble                |{$group: {_id: "$colors",n: {$sum: 1}}},
Present                 |{$sort: {n: -1}},
Present                 |{$limit: 1}


Second most popular color (by count), for brands that include the color _blue_:


```javascript
db.brands.aggregate([
  {
    $match: {
      colors: "blue"
    }
  },
  {
    $unwind: "$colors"
  },
  {
    $group: {
      _id: "$colors",
      n: {
        $sum: 1
      }
    }
  },
  {
    $sort: {
      n: -1
    }
  },
  {
    $skip: 1
  },
  {
    $limit: 1
  }
])
```
