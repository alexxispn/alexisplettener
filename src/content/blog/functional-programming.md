---
author: Alexis Plettener
pubDatetime: 2023-05-12T15:56:52.737Z
title: Functional Programming
postSlug: functional-programming
featured: true
ogImage: /assets/functional-programming.png
tags:
  - functional-programming
  - programming-paradigm
  - pure-functions
  - declarative-programming
description: I've been exploring functional programming recently and wanted to share some valuable insights and
  resources I've discovered.
---

# Functional Programming

![Functional Programming](/assets/functional-programming.png)

## Table of Contents

1. [Introduction to Functional Programming](#introduction-to-functional-programming)
    - [Definition](#definition)
    - [History and Evolution](#history-and-evolution)
    - [Functional vs. Imperative Programming](#functional-vs-imperative-programming)

2. [Functional Programming Concepts](#functional-programming-concepts)
    - [Immutability](#immutability)
    - [Pure Functions](#pure-functions)
    - [First-Class and High-Order Functions](#first-class-and-high-order-functions)
    - [Recursion](#recursion)
    - [Referential Transparency](#referential-transparency)

3. [Benefits of Functional Programming](#benefits-of-functional-programming)
    - [Predictability and Testability](#predictability-and-testability)
    - [Concurrency and Parallelism](#concurrency-and-parallelism)
    - [Modularity and Composability](#modularity-and-composability)

4. [Challenges of Functional Programming](#challenges-of-functional-programming)
    - [Learning Curve](#learning-curve)
    - [Performance Issues](#performance-issues)
    - [Debugging](#debugging)
5. [Why is Functional Programming useful to know?](#why-is-functional-programming-useful-to-know)
6. [I Need to Do Some Side Effects, What Do I Do?](#i-need-to-do-some-side-effects-what-do-i-do)
7. [Functional Programming Languages](#functional-programming-languages)
    - [Haskell](#haskell)
    - [Erlang](#erlang)
    - [Clojure](#clojure)
    - [Scala](#scala)
    - [JavaScript](#javascript)

8. [Getting Started with Functional Programming](#getting-started-with-functional-programming)
    - [Resources for Learning](#resources-for-learning)
    - [Best Practices](#best-practices)

9. [Conclusion](#conclusion)

10. [Quiz](#quiz)

## Introduction to Functional Programming

Functional programming is a paradigm or style of programming that treats computation as the evaluation of mathematical
functions and avoids changing-state and mutable data. Let's break this concept down into parts we can easily understand.

### Definition

In the simplest terms, functional programming is a style of programming where the primary method of computation is the
evaluation of functions. These functions are similar to mathematical functions, and they provide an output that depends
only on their inputs and have no side-effects (i.e., they don't modify the state of the program).

### History and Evolution

Functional programming originated from the world of mathematics, and the concepts we use in functional programming today
have a lot of their roots in Lambda Calculus, a formal system in mathematical logic.

### Functional vs. Imperative Programming

Functional programming differs significantly from imperative programming, the style most commonly taught in introductory
computer science courses. Imperative programming involves giving the computer a sequence of tasks to execute. In
contrast, functional programming involves describing what the output of a function should look like given a certain
input.

## Functional Programming Concepts

These are some of the key concepts in functional programming:

### Immutability

Immutability refers to the idea that a value cannot be changed once it's created. In a functional programming context,
this means that we should avoid changing (or "mutating") objects or variables once they've been initialized.

**Immutability example**

```javascript
const numbers = [1, 2, 3];
const numbersDoubled = numbers.map((number) => number * 2);
```

**Mutability example**

```javascript
const numbers = [1, 2, 3];
for (let i = 0; i < numbers.length; i++) {
    numbers[i] = numbers[i] * 2;
}
```

In the above example, we are not modifying the original array. Instead, we are creating a new array with the values of
the original array doubled.

### Pure Functions

A pure function is a function that, given the same input, will always return the same output and does not have any
observable side effect.

**Pure function example**

```javascript
const square = (number) => number * number;
```

**Impure function example**

```javascript
let x = 2;
const square = () => {
    x = x * x;
    console.log(x);
    return x;
};
```

In the pure function example, the function will always return the same output for the same input. In the impure function
example, the function will not always return the same output for the same input. This is because the function is
modifying the value of the variable `x` outside of its scope. Also, the function has a side effect of logging the value
of `x` to the console.

### First-Class and High-Order Functions

First-class functions are functions that can be treated like any other value in the language. Higher-order functions are
functions that take other functions as arguments, and/or return functions as results.

**First-class and higher-order function example**

```javascript
const greet = () => console.log("Hello!");
const shout = (fn) => fn().toUpperCase() + "!!!";
shout(greet); // HELLO!!!
```

In the above example, the `shout` function takes another function as an argument. This is an example of a higher-order
function.

**Non-first-class and non-higher-order function example**

```javascript
const greet = () => console.log("Hello!");
const shout = () => greet().toUpperCase() + "!!!";
shout(); // HELLO!!!
```

In the above example, the `shout` function does not take another function as an argument. This is an example of a
non-higher-order function.

### Recursion

Recursion is a method of solving problems where the solution to a particular instance of a problem depends on the
solution to smaller instances of the same problem. It's essentially when a function calls itself. Most loops can be
rewritten in a recursive style, and in some functional languages, recursion is the primary
way to iterate.

**Recursion example**

```javascript
const countDown = (number) => {
    if (number === 0) {
        return;
    }
    console.log(number);
    countDown(number - 1);
};
countDown(10);
```

In the above example, the `countDown` function calls itself until the `number` argument is equal to 0.

**Non-recursive example**

```javascript
const countDown = (number) => {
    for (let i = number; i > 0; i--) {
        console.log(i);
    }
};
countDown(10);
```

In the above example, the `countDown` function uses a `for` loop to iterate over the `number` argument.

### Referential Transparency

Referential transparency is a property of pure functions where calling a function with the same argument will always
produce the same result. This is closely linked to the concept of a pure function.

**Referential transparency example**

```javascript
const add = (a, b) => a + b;
const result = add(2, 3); // 5
```

In the above example, the `add` function is pure, so we can replace the function call with its value without changing
the behavior of the program.

**Non-referential transparency example**

```javascript
const addRandomNumber = (a) => a + Math.random();
const result = addRandomNumber(2); // 2.123456789
```

In the above example, the `addRandomNumber` function is impure, so we cannot replace the function call with its value
without changing the behavior of the program.

## Benefits of Functional Programming

Functional programming has several benefits:

### Predictability and Testability

Since functional programming avoids changing-state and mutable data, the programs are more predictable and easier to
test.

### Concurrence and Parallelism

Functional programming is well-suited for concurrent and parallel programming because it uses immutable data structures
and avoids side effects.

### Modularity and Composability

Functional programming promotes modularity and composability. Functions are building blocks that can be composed to
create complex operations.

## Challenges of Functional Programming

While functional programming has its benefits, it comes with its own set of challenges:

### Learning Curve

For programmers who are familiar with the imperative programming paradigm, there can be a steep learning curve to
understand the functional programming paradigm. The concepts and techniques (such as avoiding mutable state and side
effects) can initially be difficult to grasp.

### Performance Issues

Functional programming languages can sometimes be less efficient in their use of memory and CPU than imperative
languages. Also, because functional programming uses recursion extensively, this can lead to performance issues.

### Debugging

Debugging functional programs can be challenging, especially when dealing with recursion and higher-order functions.

## Why is Functional Programming useful to know?

Learning functional programming, even if you don’t use it extensively in your projects, can still be incredibly useful
for several reasons:

- **Better abstraction**: Functional programming provides powerful abstractions that allow for more succinct and
  expressive code. Higher-order functions, pure functions, and immutability can lead to clearer and more concise code.

- **Easier testing and debugging**: Since functional programming emphasizes pure functions, this leads to less shared
  state and fewer side effects. This, in turn, makes your programs easier to test and debug.

- **Concurrency and parallelism**: With the rise of multi-core and distributed systems, concurrency and parallelism are
  increasingly important. Functional programming languages handle these with aplomb.

- **Job market**: Knowledge of functional programming is in demand in the job market. Languages like Scala, Erlang, and
  Clojure are often used in industries such as data science, telecommunications, and finance.

## I Need to Do Some Side Effects, What Do I Do?

In the real world, you can't always avoid side effects. You often need to interact with a database, change the
filesystem, make a network request, or interact with the outside world in some other way.

Functional programming doesn't say that you should never have side effects. Instead, it encourages you to isolate and
control them. Side effects are contained in specific functions, and the data flow through the application is made as
clear as possible.

In some functional languages, there are specific constructs to handle side effects while keeping functions pure. For
example, in Haskell, this is achieved using the IO monad. In JavaScript, you might use promises or async/await to handle
asynchronous side effects in a functional style.

Remember, it's all about managing side effects, not eliminating them completely. The goal is to make our code more
understandable, easier to test, and easier to reason about.

For example, if you need to change the color of a button in your app, you can define a pure function that calculates the
color based on some inputs, and then have a separate function that handles the side effect of updating the UI with that
color.

```javascript
// Pure function that calculates the color of a button
const getButtonColor = (isDisabled) => isDisabled ? "gray" : "blue";
// Side effect that updates the UI
const updateButtonColor = (color) => {
    const button = document.getElementById("myButton");
    button.style.color = color;
};

// Calculate the color
const buttonColor = getButtonColor(true);
// Update the UI
updateButtonColor(buttonColor);
```

## Functional Programming Languages

There are several programming languages that support functional programming:

### Haskell

Haskell is a pure functional programming language, which means that all functions in Haskell are pure functions by
default.

### Erlang

Erlang is a functional programming language that's used primarily for concurrent programming.

### Clojure

Clojure is a modern functional programming language that's a dialect of Lisp and runs on the Java Virtual Machine.

### Scala

Scala is a hybrid functional programming and object-oriented programming language that runs on the Java Virtual Machine.

### JavaScript

JavaScript is a multi-paradigm programming language that supports functional programming.

## Getting Started with Functional Programming

Interested in learning more about functional programming? Here are some resources and best practices:

### Resources

- [Learn You a Haskell for Great Good!](http://learnyouahaskell.com/) - A fun way to learn Haskell.
- [Erlang - A Course for Beginners](https://www.futurelearn.com/courses/functional-programming-erlang) - A free online
  course on Erlang.
- [Clojure for the Brave and True](https://www.braveclojure.com/) - An online book for learning Clojure.
- [Scala School](https://twitter.github.io/scala_school/) - A set of lessons covering Scala concepts.
- [Functional Programming in JavaScript](https://github.com/luijar/functional-programming-js) - A GitHub repository with
  resources to learn functional programming concepts in JavaScript.

### Best Practices

- Start small: Begin with understanding and implementing basic functional programming concepts such as pure functions,
  immutability, and recursion.
- Practice: The more you practice writing functional code, the better you will understand the concepts.
- Code review: Have others review your code to ensure you're properly applying functional programming concepts.

## Conclusion

Functional programming is a powerful programming paradigm that offers several benefits such as predictability,
modularity, and the ability to handle concurrent processing. While it does come with challenges, understanding and using
functional programming can make you a better programmer and expand your thinking about problem-solving in coding.

## Quiz

```javascript
const add1 = (a, b) => a + b;
const add2 = (a, b) => {
    const result = a + b;
    return result;
};
const add3 = (a, b) => {
    const result = a + b;
    console.log(`${a} + ${b} = ${result}`);
    return result;
};

const generateRandomNumber = () => Math.random();

const checkGuess = (guess, secretNumber) => guess === secretNumber;

const displayMessage = (message) => {
    console.log(message);
};

const updateScore = (score, points) => score + points;

const saveScore = (score) => {
    // Saving score to external storage
};

const resetGame = () => {
    // Resetting game state
};

const generateHint = (secretNumber) => `The secret number is between 1 and ${secretNumber}`;

const getHighScore = () => {
    // Retrieving high score from external storage
};
```

<details>
<summary>Solution</summary>

* The first function (`add1`) is a pure function because it always returns the same output for the same input and
  has no side effects.
* The second function (`add2`) is a pure function because it always returns the same output for the same input and
  has no side effects.
* The third function (`add3`) is an impure function because it has a side effect of logging to the console.
* The `generateRandomNumber` function is a non-pure function because it produces different outputs each time it is
  called.
* The `checkGuess` function is a pure function because it compares the `guess` with the `secretNumber` and returns a
  boolean without any side effects.
* The `displayMessage` function is a non-pure function because it involves a side effect of interacting with the
  user interface by displaying a message.
* The `updateScore` function is a pure function because it takes the current `score` and `points` earned from the
  guess and returns the updated score without modifying external state or having side effects.
* The `saveScore` function is a non-pure function because it involves a side effect of saving the score to an
  external storage.
* The `resetGame` function is a non-pure function because it involves modifying the external state by resetting the
  game.
* The `generateHint` function is a pure function because it generates a hint for the `secretNumber` and returns it
  without modifying external state or having side effects.
* The `getHighScore` function is a non-pure function because it involves a side effect of retrieving the high score
  from an external storage.

</details>


