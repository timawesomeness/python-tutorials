# Tutorial 2 - Functions and input

###### You will build a simple number guessing game in this tutorial.

In this tutorial you will learn:

* Functions - what a function is, how to write one, how to use them
* Input - how to prompt for and read input from the terminal

Create a new project in PyCharm (File > New Project...) named `2`. Also create a file named `guess_number.py`. We will come back to that file throughout the tutorial.

## Part 1 - Functions

Functions were briefly mentioned in the previous tutorial - a function essentially take an optional input (called arguments), performs some action, and optionally returns a value.

Create a file named `functions.py`.

Let's start by writing a function that adds two numbers together and returns the result.

A function starts with the `def` keyword, then the name of the function, then its arguments, then a code block defining the function:

```python
def add(first, second):
```

We're going to return the sum of the two numbers using the `return` statement briefly mentioned in the previous tutorial.

```python
def add(first, second):
    return first + second
```

After that function, add a `print(add(1, 2))` line. This, expectedly, will calculate the sum of 1 and 2, and print the result.

Run the code. It should output `3`.

Write a similar function called `subtract` that takes two numbers and returns their difference. Make sure to use code completion! Then add another print line which prints the difference of 10 and 5. Run your script - it should output `3` and then `5`.

Let's start writing our number guessing game. This game will generate a random number between 1 and 100, then ask the user to guess it while providing hints. Switch to your `guess_number.py` file. 

We're going to need a random number for our game, so start by importing the `random` module. Then we need to create a variable and initialize it with to a random number that the user will guess.

```python
import random

number = random.randrange(1, 101)
```

What does the `random.randrange` function do? Use PyCharm's quick documentation shortcut (Ctrl+Shift+Space) to find out. `randrange`'s first argument is inclusive, and its second argument is exclusive, which is why we're using 101.

Let's write a function to check if a guess is higher or lower than our random number and print a hint. It should be named `higher_or_lower` and needs to have one argument, the number we're going to test. In the function you should use an if statement to test if the number passed as an argument is greater than `number`, if yes the print out something like "Guess lower!", otherwise print something like "Guess higher!". The function will not return anything.

## Part 2 - Input



