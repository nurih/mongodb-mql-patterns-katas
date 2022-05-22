# Kata 6 
## Combined

Instructions:

1. Open kata 5 playground by clicking [https://mongoplayground.net/p/9W8xDcaM7hY](https://mongoplayground.net/p/9W8xDcaM7hY)
1. Inspect the dataset "brands" in the leftmost column to familiarize yourself with the documents you will be querying.
1. What document-pattern do the documents exhibit?
1. Consider the query below. Which of the MQL stages belong to which pipeline pattern part (_Gather_, _Assemble_ or _Present_)?:
   ```
   db.brands.aggregate([
        {$match: {colors: "blue"}},
        {$unwind: "$colors"},
        {$group: {_id: "$colors",n: {$sum: 1}}},
        {$sort: {n: -1}},
        {$limit: 1}
    ])
   ```
1. Write a query to answer the question: For brands which have the color _blue_ as one of their colors, what is the second most popular color?

