# Building a Queue with Haskell

Building a queue with Haskell involves the following steps:

1. Model a queue with its type and data signatures. 

```
data Queue a = Queue [a] deriving (Show)
```

2. Now we need to declare the types of our basic operation. For the push operation we need receive an element and a Queue and push it onto it, while pop needs to return the element, and the new modified Queue.

```
push  :: a -> Queue a -> Queue a
pop :: Queue a -> (a, Queue a)
peek :: Queue a -> a
```

The entire implementation is below..

```
data Queue a = Queue [a] deriving (Show)

push :: a -> Queue a -> Queue a
push e (Queue es) = Queue (es ++ [e])

-- Precondition: Queue is not empty
pop :: Queue a -> (a, Queue a)
pop (Queue xs) = (head xs, Queue $ tail xs)

-- Precondition: Queue is not empty
peek (Queue (x:xs)) = x
```

However, this implementation is inefficent because we are using the list concatentation operator (++), which takes time proportional to the length of the list. Therefore, the push operation would be in O(n) and not constant time. 


#### Exercise: Try to implement a Queue with a push operation that runs in constant time



### Reccomendations for Future Reading:
- [Data Structures in Haskell](https://en.wikibooks.org/wiki/Haskell/Other_data_structures)
- [Real World Haskell - Data Structures](http://book.realworldhaskell.org/read/data-structures.html)