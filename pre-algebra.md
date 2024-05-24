## Pre-algebra

### Understanding factor pairs

```haskell
[x | x <- [1..6], 6 `mod` x == 0]
```
This list comprehension directly generates the factors of 6 by iterating over the list from 1 to 6 and checking which numbers divide 6 without a remainder. 
When you run this in the Haskell interpreter (GHCi), it will output the list of factors of 6: `[1, 2, 3, 6]`
