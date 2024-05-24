In Haskell, a binary tree is a recursive data structure that can either be empty (Nil) or a node containing a value and two subtrees (Node).
```haskell
data Tree a = Nil
            | Node a (Tree a) (Tree a)
```

