# Kata 3
## Liberate

Instructions:

1. Open kata 3 playground by clicking [https://mongoplayground.net/p/wmLR3kYmxCw](https://mongoplayground.net/p/wmLR3kYmxCw)
1. Inspect the dataset "brands" in the leftmost column to familiarize yourself with the documents you will be querying.
1. What document-pattern do the documents exhibit?
1. Create an MQL pipeline to return the document `_id` and a **single** color from the `colors` array of each document.
1. Similar to the above, add an index /offset to each document representing the offset of the color in the original array. The offset should be in an output field named `originalOffset`.
1. Similar to the above, but return all documents, even if they did not have items in their original `colors` array.

