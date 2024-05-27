# Algebra 1

## Evaluating an expression with one variable

Given the following expression `5t + 1`, evaluate the expression when `t=1`, `t=8`, and `t=10`.
```haskell
expression = \t -> 5*t + 1
map expression [1,8,10]
[8,43,53]
```
## Introduction to variables

Evaluate the expression `9 - z` when `z = 4`
```haskell
(\z -> 9 - z) 4
5
```
Evaluate `2y` when `y = 6`
```haskell
(\y -> 2*y) 6
12
```
Evaluate the expression `7 + 4b` when `b = 3`
```haskell
(\b -> 7 + 4*b) 3
19
```
Evaluate the expression `8/d + 3` when `d = 4`
```haskell
(\d -> 8/d + 3) 4
5
```
Challenge problem: Evaluate `e*e - 5*e` when `e = 5`
```haskell
(\e -> e*e - 5*e) 5
0
```
Complete the table to evaluate `2x` at different values of `x`
```haskell
map (\x -> 2*x) [1,2,3,4,5,6]
[2,4,6,8,10,12]
```

## Evaluating expression with two variables

Evaluating expressions with multiple variables involves substituting given values for each variable and simplifying the expression. By replacing variables with their corresponding values, we can easily compute the result of expressions, even for more complex examples with multiple terms and operations. Created by Sal Khan.

Let's break down the evaluation of the expression `(\a -> \b -> a + b) 7 2`

```haskell
(\a -> a + 2) 7
9
(\b -> b + 7) 2
9
(\a -> \b -> a + b) 7 2
9
```

`xy - y + 3x`:
```haskell
(\x -> \y -> x * y - y + 3 * x) 3 2
13
(\x -> x * 2 - 2 + 3 * x) 3
13
(\y -> 3 * y - 2 + 3 * 3) 2
13
```

Evaluate ‍`3 + j*k + k*k*k` when `j=2` and `k=6`
```haskell
(\j -> \k -> 3 + j * k + k*k*k) 2 6
231

(\r -> \s -> 8 * r - r * s) 6 5
18

(\f-> \g-> \h-> f*f*f + 11*g - 4*h) 3 2 7
21
```



The expression `(\a -> \b -> a + b)` is a lambda function (also known as an anonymous function) that takes two arguments, `a` and `b`.
This lambda function can be read as: "a function that takes an argument a and returns another function that takes an argument b and returns the result of a + b."


## Linear equations with variables on both sides

**Why we do the same thing to both sides: Variable on both sides**

https://youtu.be/vkhYFml0w6c
Let's say we have a scale and on it's two sides the relation: `3y + 3 = y + 7`. We can take multiple paths from here. Let's remove a `y` from both sides so that the scale stays balanced. This leaves us then with `2y + 3 = 7`. Sal is showing it in a visual way by removing the `y` from the scale on both ends. Then we remove the `3` and the `3` by subtracting it from the `7` on the other side which leaves us with: `2y = 4`. Then divide both sides by `2` which is: `y = 2`

Let's try something like this in Haskell:
```haskell
-- Given equation: 3*y + 3 = y + 7

-- Collect coefficients and constants
let a = 3  -- Coefficient of y on the left-hand side
let b = 3  -- Constant on the left-hand side
let c = 1  -- Coefficient of y on the right-hand side
let d = 7  -- Constant on the right-hand side

-- Calculate the value of y
let y = (d - b) / (a - c)

-- Output the value of y
y
```

