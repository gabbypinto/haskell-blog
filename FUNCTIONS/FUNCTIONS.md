# FUNCTIONS

### Higher Order Functions
Higher-order functions are functions that take other functions as arguments or returns a function as a result. 

An example of a higher order function is...

```
app:: (a->b) -> a -> b
app fx = fx

add1 :: Int ->  Int
add1 x = x + 1
app add1 1

=> 2
```

In fact, many functions in the haskell libraries are higher-order. Some of them include map and fold. 

Below is an example that shows the difference between higher-order functions and other types of functions are...

For instance, we could write..

```
doubleList [] = []
doubleList (x:xs) =  2*x : doubleList xs
```
and 

```
tripleList [] = []
tripleList (x:xs)  = 3*x : tripleList xs
```

we can write ....

```
multList n [] = []
multList n (x:xs) = n*x : multList n xs
```
and define them as...

```
tripleList = multList 3
doubleList = multList 2
```

So clearly the advantage of higher-order functions is concise code and less error prone defintions.

### Anonymous Functions

An anonymous function is function without a name, and a lambda abstraction. These functions essentially increment its parameters...for example in GHCI...

```
Prompt> (\x -> x + 1) 4
5 :: Integer
```

Another example is ...
```
Prompt> (\x y -> x + y) 3 5
8 :: Integer
```
