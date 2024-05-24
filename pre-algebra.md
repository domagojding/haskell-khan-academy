## Pre-algebra

### Understanding factor pairs

```haskell
[x | x <- [1..6], 6 `mod` x == 0]
```
This list comprehension directly generates the factors of 6 by iterating over the list from 1 to 6 and checking which numbers divide 6 without a remainder. 
When you run this in the Haskell interpreter (GHCi), it will output the list of factors of 6: `[1, 2, 3, 6]`

specific example variation:
```haskell
let xs = [1..16] in [x | x <- xs, 16 `mod` x == 0]
```
Another variation without the `mod` but looks worse:
```haskell
[x | x <- [1..6], elem (6 `div` x) [1..6], 6 == x * (6 `div` x)]
```

Generalized function:
```haskell
factors   :: Int -> [Int]
factors a = [x | x <- [1..a], a `mod` x == 0]
```
Links:
* https://www.tutorialspoint.com/haskell-program-to-display-factors-of-a-number

We are looking for pairs that have a product of ‍ 30. How would we do that using haskell?
To find pairs of numbers whose product is 30 using basic Haskell, you can use a list comprehension that generates all pairs (x, y) where both x and y come from a specified range, and then filter those pairs where the product x * y equals 30.

```haskell
λ [(x,y) | x <- [1..30], y <- [1..30], x * y == 30]
[(1,30),(2,15),(3,10),(5,6),(6,5),(10,3),(15,2),(30,1)]
```
A generalized function would be:

```haskell
λ factorPairs n = [(x,y)|x <- [1..n], y <- [1..n], x*y == n]

λ factorPairs 66
[(1,66),(2,33),(3,22),(6,11),(11,6),(22,3),(33,2),(66,1)]
```

### 4th Grade, Unit 6, Identity factor

One of the test questions was which of the following numbers is a factor of ‍some number? Now let's say we write a haskell program that would give a true or false when we ask if such a number is a factor of some number:

```haskell
-- Define the function factorOf
factorOf :: Int -> Int -> Bool
factorOf n x = n `mod` x == 0
```
Write a Haskell function that takes a list of numbers and returns a list of tuples where each tuple contains the number and a boolean indicating whether it is a factor of a given number. This is because in the test we are given a list of numbers but some of those are incorrect solutions. So how would we write a program
that would give that information as well:

```haskell
λ checkFactors n xs = [(x, factorOf n x) | x <- xs]
λ checkFactors 49 [4,2,7,9]
[(4,False),(2,False),(7,True),(9,False)]
```
### Multiples

Which of the following numbers is a multiple of 14: 69, 70, 75, 80, 85

```haskell
λ [(x, x `mod` 14 == 0) | x <- [69,70,75,80,85]]
[(69,False),(70,True),(75,False),(80,False),(85,False)]
```
Another variation without using the `mod` function:
```haskell
λ [(x, x `div` 14 * 14 == x) | x <- [69,70, 75,80,85]]
[(69,False),(70,True),(75,False),(80,False),(85,False)]
```


