# Concepts of Functional Programming in Javascript
## What is functional programming?
#### Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data 
#### The first fundamental concept we learn when we want to understand functional programming is pure functions. But what does that really mean? What makes a function pure? So how do we know if a function is pure or not? Here is a very strict definition of purity:
1. It returns the same result if given the same arguments (it is also referred as deterministic)
2. It does not cause any observable side effects
3. It returns the same result if given the same arguments
#### Imagine we want to implement a function that calculates the area of a circle. An impure function would receive radius as the parameter, and then calculate radius * radius * PI
##### For the parameters radius = 10 & PI = 3.14, we will always have the same the result: 314.0
##### For the parameters radius = 10 & PI = 42, we will always have the same the result: 4200
## Reading Files
#### If our function reads external files, it’s not a pure function — the file’s contents can change.
## Random number generation
#### Any function that relies on a random number generator cannot be pure.
#### It does not cause any observable side effects
#### Examples of observable side effects include modifying a global object or a parameter passed by reference. Now we want to implement a function to receive an integer value and return the value increased by 1
## Pure functions benefits
#### The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:
1. Given a parameter A → expect the function to return value B
2. Given a parameter C → expect the function to return value D
##### A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.

## Immutability
#### When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.In Javascript we commonly use the for loop. This next for statement has some mutable variables.

## Functions as first-class entities

#### The idea of functions as first-class entities is that functions are also treated as values and used as data. Functions as first-class entities can:
1. refer to it from constants and variables
2. pass it as a parameter to other functions
3. return it as result from other functions
#### The idea is to treat functions as values and pass functions like data. This way we can combine different functions to create new functions with new behavior.

## Higher-order functions
#### When we talk about higher-order functions, we mean a function that either:
1. takes one or more functions as arguments, or
2. returns a function as its result
#### The doubleOperator function we implemented above is a higher-order function because it takes an operator function as an argument and uses it. You’ve probably already heard about filter, map, and reduce. Let's take a look at these.
## Filter
#### Given a collection, we want to filter by an attribute. The filter function expects a true or false value to determine if the element should or should not be included in the result collection. Basically, if the callback expression is true, the filter function will include the element in the result collection. Otherwise, it will not. A simple example is when we have a collection of integers and we want only the even numbers.Imperative approach
#### An imperative way to do it with Javascript is to:
1. create an empty array evenNumbers
2. iterate over the numbers array
3. push the even numbers to the evenNumbers array

## Map
#### The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.
## Reduce
#### The idea of reduce is to receive a function and a collection, and return a value created by combining the items.
