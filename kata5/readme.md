# Kata 5
## Shape Up

Instructions:

1. Open kata 5 playground by clicking [https://mongoplayground.net/p/ejVe34fbZdi](https://mongoplayground.net/p/ejVe34fbZdi)
1. Inspect the dataset "scores" in the leftmost column to familiarize yourself with the documents you will be querying.
1. What document-pattern do the documents exhibit?
1. Which _pipeline sequence_ part  is a likely place for `$project` MQL stage (_Gather_, _Assemble_ or _Present_)?
1. For each document, output the `name` and `score` fields only.
1. For each document, calculate a bonus score: add 5 points to each original `score` value, and place the value in a field named `boosted`. Output both the original score as well.
1. For each document, output the `subject`, and a sub-document named `year_and_month`. In the sub-document place the year from the original `dt` field, and the month from the original `dt` field. Name those fields as you wish.

