# Tutorial 1 - Intro to PyCharm, Python syntax, and flow control

###### You will not be building a full program in this tutorial.

In this tutorial you will learn:

* The basics of PyCharm and some simple tips to get the most out of it
* The basic syntax of Python
* Simple Python flow control

Start with creating a folder anywhere on your computer to store these tutorial projects in.

## Part 1 - PyCharm

Launch PyCharm. You should see the following dialog that lets you create a new project or open an existing one.

![](https://i.imgur.com/wiH0VkK.png)

You will very rarely interact with the dialog, as it only pops up when you didn't previously have a project open.

Click "Create New Project". Set the location as a subfolder of the previous folder you created named `1`. That will be the project directory we use for this tutorial. Click "Create".

PyCharm will now create your new project. Once that is finished, you will see the main PyCharm interface. It should look something like this:

![](https://i.imgur.com/NWLpIT7.png)

We care specifically about three main things:

1. The Project panel - This displays your project, its files, any external libraries you use, and any scratch files you create. This is effectively a file browser for your project built into PyCharm.
2. The main editor area - This is where the editor will be displayed if you open a file. It is highly configurable and can be split to show multiple files at once.
3. Several other panels and tools:
    * The Structure panel - this displays the overall structure of a file. It can be useful when working with large or complex files to quickly jump to different methods and other things in the file.
    * The Python Console - this displays a Python interpreter that you can type python code directly into and execute it in real time. We will make use of this later, after you're familiar with running code from a file.
    * Terminal - this displays a system terminal. Mostly useful on Linux where you want to navigate around your project in a terminal.
    * TODO - this displays `# TODO` comments in your code. Useful when you want to remember to finish something later. We will make use of this in more complex projects.

Let's create a Python file to learn some more PyCharm features. Right click on your project folder (`1`) at the top of the project panel and select New > Python File. Name it `pycharm.py`. It will then open in the main editor area.

First, let's learn about Code Completion. Code Completion is a very powerful feature of most IDEs (integrated development environments) which allows you to type less and spend less time trying to find the name of something. Copy and paste the following code into the editor:

```python
impo

numbers = [1, 2, 3, 4, 5]

pri
```

Position your cursor after `impo` and press Ctrl+Space, the completion shortcut. You'll see a dialog pop up that offers some suggestion, `import` being the first. Press enter to autocomplete `import`. Now type `sta`. You'll see `stat`, `statistics`, and several other options pop up. Arrow down to `statistics` and press enter.

Then, position your cursor after `pri` and press Ctrl+Space. This should insert `print()`, the only completion option available, and your cursor will be inside the parentheses. Try typing the following while relying on code completion for every word: `statistics.mean(numbers)`.

Next, let's learn about another very useful feature of PyCharm. Position your cursor anywhere in the word `print` and press Ctrl+Shift+Space. This opens the quick documentation dialog which shows any available documentation about something. You will use this frequently to find out what an unfamiliar function does. What does it say the `print` function does?

Finally, let's learn how to run the file we just created. Click the ▶ button in the toolbar. The Run panel will pop up at the bottom of the window with the result of what we just ran. The output of our file was `3`, which will be displayed there.

## Part 2 - Python syntax

Let's start by analyzing the file we just created.

The first line, `import statistics`, is an *import statement*. A *statement* is a keyword that performs some functionality. For example, an import statement imports (provides your code access to) a library (a package of existing code meant to be used in another project) or a file so that you can use the variables, functions, classes, etc. in it. There are many other statements in Python, such as `return` (return an object from a function), `pass` (do nothing), and `del` (delete a variable).

The next line, `numbers = [1, 2, 3, 4, 5]`, assigns a list of 1 to 5 to the variable `numbers`. Let's deconstruct this line piece by piece:

* `number` - This is a *variable*, a type of Python *object* (an object is essentially a thing that exists when your program is running). Because it hasn't previously been used, this line defines and *initializes* (sets the initial value of) it.
* `=` - This is the *assignment operator*, it sets the value of a variable. An *operator* is something that performs a (typically mathematical) action on two other things but isn't a function. Some other examples are `+` (addition), `*` (multiplication), and `**` (exponent). As a side note, `=` is NOT also used for checking equality like in math.
* `[1, 2, 3, 4, 5]` - This specifies a *list* of 1 to 5. A list is a Python object that (unsurprisingly) holds a list of other objects. It consists of square brackets surrounding a comma-separated list of objects. This is one of several data types you will make frequent use of.

The next line, `print(statistics.mean(numbers))`, calls two *functions*. A function looks like `name(arguments)`, takes (optional) arguments as a comma-separated list inside the parentheses, does something, and optionally returns a result. You may hear the word "method" used similarly; we will learn the difference between a method and a function later.

* The `print` function is used to print data to the console. You will use it more than any other function in Python. 
* `statistics.mean` calls the `mean` function from the `statistics` library, which accepts a list (which we defined earlier as `numbers`) as an argument and returns the mean of that list.

Because `statistics.mean` is inside `print`'s parentheses, it is called first, and the result that it returns is the argument that `print` is executed on.

Next, create a new file named `python_syntax.py` as described in the previous part. We will learn some more syntax using this file.

Let's start by defining a variable named `var_1` and initializing it to `"chicken"`. Your result should look like `var_1 = "chicken"`. Let's break down the new part of this line: a string. A string is simply any text. It is wrapped in single (`'`) or double (`"`) quotes (some people prefer single, I prefer double because that matches other programming languages).

Next, let's learn how *blocks* of code are designated. Type in the following, using code completion as much as possible (no copy-pasting!):

```python
if True:
    print(var_1)
    print(1)
    print(2)
```

I'm sure you'll notice the *if statement*, we'll come back to it in the next part. We're interested in what comes after it: the `:`. A colon indicates the start of a block of code, and is valid after many things such as if statements. Next, you'll see that the three subsequent lines are indented with four spaces; this indicates that these lines are in the block of code started by the `:`. Python doesn't care if you use tabs or spaces (though spaces are the standard) as long as all lines of the code block are indented equally and you use tabs or space consistently (otherwise you'll get a syntax error). PyCharm will automatically type four spaces when you press tab.

Finally, let's learn about *comments* (text that isn't executed by the Python interpreter) which are used to document your code (a very important task!). At the end of the `print(var_1)` line add `  # Prints chicken`. Comments in Python start with a `#` and go until the end of the line.

As you may have noticed, Python doesn't rely on heavy syntax like many programming languages. Parentheses are used sparingly, blocks of code are defined by indentation as opposed to braces, and very little structure is required. Those things can be argued as advantages or disadvantages, but for learning to program they make life much easier.

To finish up this part, let's run the code. It should output:

```
chicken
1
2
```

## Part 3 - Flow control

Flow control is how we make decisions, execute code in a specific order, loop code, etc. You may be familiar with many things in flow control: if statements, while loops, for loops, etc.

Create a new file named `flow_control.py` as explained previously. Let's create a simple if-else statement that executes some code (type it by hand with code completion, no copy-pasting!):

```python
if 1 > 2:
    print("math is broken!")
else:
    print("math isn't broken")
```

An if statement starts with the keyword `if`, followed by a condition (`1 > 2`), then a code block. If the condition is true, the code block is executed. An `else` statement triggers if the proceeding if statement's condition was false.

Run the code, it should output `math isn't broken`.

We can chain an if statement onto an else statement to create an `else-if`. Modify the code to the following:

```python
if 1 > 2:
    print("math is broken!")
else if 1 < 2:
    print("math isn't broken")
```

If the first condition (`1 > 2`) is false (which it is), Python will go to the else-if statement, check if its condition (`1 < 2`) is true (which it is), and if so, execute the else-if's code block.

Run the code, it should still output `math isn't broken`.

Normally we check a variable against something in an if statement. Let's do that - modify the code to the following:

```python
var_1 = 1
if var_1 != 1:
    print("math is broken!")
else if var_1 == 2:
    print("math isn't broken")
```

Here we see a variable being used in an if-else-if statement, as well as the equality and inequality operators. `!=` checks if the first thing is not equal to the second thing. `==` checks whether the first thing is equal to the second thing (as opposed to just `=` in math). Both of these, as well as the `<` and `>` that we used before, "return" a value - True or False - indicating their result. If you want, you can open the Python Console mentioned earlier, and run `print(1 == 1)` to demonstrate this.

Run the code, it should still output `math isn't broken`.

Next, let's move on to some loops. Python has two types of loop: a `while` loop, and a `for` loop. A while loop executes the loop as long as the condition is true. A for loop iterates through something and executes for each item. Python's for loop is similar to a `for-each` loop in other programming languages.

Starting with a while loop, add the following to the file (no copy-pasting, blah blah blah):

```python
counter = 0

while counter < 5:
    print(counter)
    counter += 1
```

This code does several things. Read through it and explain to yourself what each line does. You should be able to figure it out even though we haven't explained everything.

Let's look at the while loop. Python checks the condition (`counter < 5`), and if true, runs the code block, then checks the condition, runs the code block, etc. until the condition is false.

Run the code, it should output the previous `math isn't broken` and the following:

```
0
1
2
3
4
```

Slightly off-topic, let's look at the `counter += 1` line. The `+=` operator adds the right side to the variable on the left side. It could also be written as `counter = counter + 1`. There are several similar operators: `-=`, `/=`, `*=`, `**=`.

Let's see what this code does (you should have figured this out already):

* Initializes `counter` to 0
* Checks if `counter` is less than 5
* If so, runs the code block, which prints the value of `counter` and adds 1 to `counter`
* Checks the condition again, runs the code again, etc. until `counter` is not less than 5

Now, on your own, modify the code so that `counter` starts at 5, the loop runs while `counter` is greater than 2, and 1 is subtracted from `counter` instead of added. Run it, and it should output your "math isn't broken" and the following:

```
5
4
3
```

Next, you'll learn about for loops. After the previous code, add the following (no copy pasting, use code completion, you can skip typing the comment):

```python
letters = ["a", "b", "c", "d"]  # Create a list, letters, of the strings, a, b, c, d. You should recognize this from earlier

for letter in letters:
    print(letter)
```

This for loop iterates through `letters` and prints each letter. Specifically, it starts at `"a"`, assigns it to `letter`, prints `letter`, assigns `"b"` to `letter`, prints `letter`, etc. for each element in `letters`. You will use for loops frequently, any time you need to perform the same action on multiple items.

Run the code, it should print your previous "math isn't broken", 5 4 3, and the following:

```
a
b
c
d
```

Now it's your turn to code something: a for loop with an if-else statement in it. Create a file named `1_final.py`. Create a list of numbers from 0 to 5. Make a for loop that iterates over that list. Inside the for loop, use an if statement to check if the current item equals 3; if so, print "three", otherwise print the current item. Then, run that code. If you've done it correctly it will output:

```
0
1
2
three
4
5
```

#### Congrats, you've learned the very basics of Python.

Tutorial 2 will build on this, and cover functions and input.
