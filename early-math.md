## Early Math

### Generate a list of strings or numbers or some length
So one of the early math review assignments is "Count with small numbers" in which there is a picture of a flower and one is supposed to drag and drop that
flower object into a box six times. The question is: Put 6 flowers in a box. Now let's say we restate that with put 6 numbers in a list. We could use the `replicate` function in the interpreter like this:
```haskell
replicate 6 "dandelion"
```
Or with a number:
```haskell
replicate 6 5
[5,5,5,5,5,5]
```
Other variations such as taking 6 strings from an infinite list of flowers:
```haskell
take 6 (repeat "dandelion")
["dandelion","dandelion","dandelion","dandelion","dandelion","dandelion"]
```
Or using list comprehensions where we have an empty unit where we fill in the values or a list that ranges between 1 and 6:
```haskell
[ "dandelion" | _ <- [1..6] ]
```
### Find 1 more or 1 less than a number
```haskell
oneMore n = n + 1
oneMore 1
2

oneLess n = n - 1
oneLess 1
0
```
