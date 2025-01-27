# Fundamentals

## What is Python

- high level
- dynamically typed
- interpreted
- interoperates well with c
- used in data science
- useful for writing scripts

High Level means Python abstracts away the hardware details and differences between operating systems, at least as well as it can. This is as opposed to low level languages like C and assembly. Those languages are more fiddly and require more specialized knowledge to write, in exchange for performance. Most popular languages in use now are high level.

Dynamically Typed means that when we get to variables, any variable can hold any type of value. This is like languages like Ruby and JavaScript, and unlike statically typed languages like C, C++, Java, C#, and so on. Dynamically typed languages are thought to be easier to write, but statically typed languages can make grantees and find issues before you even run your code.

Interpreted means there is a program on your computer, called an interpreter, that reads your Python scripts and follows what those scripts say to do. Imagine the interpreter as a little robot and our scripts as sets of instructions for that robot to execute. This is as opposed to compiled languages. With those, a program called a compiler takes the code you write and translates it into native machine code your computer can understand. Interpreted languages tend to be slower, that little robot has some overhead, but it lends itself to languages that are high level and portable.

Python interoperates well with C. We won't be touching these capabilities in this class, but you can call code written in C and C++ from Python relatively easily. This lends itself well to writing high level code that has good performance.

Python is often used in data science. It has extensive library support for collating, analyzing, and visualizing data.

For my purposes though, I use it for writing scripts. If I want to automate a complex task but don't want to write a whole dedicated program a few Python scripts are the way to go.

## Data Types

- Int
- Float
- String
- Boolean
- None

## Expressions

An expression is a bit of code that evaluates to something.

### Literals

Let's look at our Hello World program again:

```python
print("Hello World!")
```

The string "Hello World!" appears in our source code, it's not read from a file or input from the user or something like that. That makes it a literal. Here is another example.

```python
print(10)
```

Likewise, the value `10` is embedded in the source code itself. We'll see the alternative... right now actually.

### Operators

```python
print(5 + 5)
```

It shouldn't be any great wonder what the above prints when we run it. Here we have two literal values and we are adding them with the plus sign. The plus sign is an example of an operator, it performs an operation. In this case the operation is addition. Let's look at some more examples.

```python
print(5 + 5) # prints 10
print(5 - 5) # prints 0
print(5 * 5) # prints 25
print(5 / 5) # prints 1.0
```

No surprises here. The only curious one is the last one, you'll notice it prints `1.0` instead of just `1`. Why? Well in Python when you divide one number by another the result is always a float, even if the input numbers were integers.

```python
print(5 / 2) # prints 2.5
```

Similarly if you add or multiply a float with an integer the result is a float. This is an example of something called Type Coercion, and it's otherwise pretty rare in Python. JavaScript and PHP are infamous for it though. Just file that away somewhere.

```python
print(5 + 5 * 2)    # prints 15
print( (5 + 5) * 2) # prints 20
```

Order of operations is respected. So multiplication and division go before addition and subtraction. You can use parentheses to ensure part of the expression is evaluated first.

Finally there are the comparison operators.

```python
print(5 == 5) # prints True
print(5 != 2) # prints True
print(2 < 5)  # prints True
print(2 > 5)  # prints False
print(5 <= 5) # prints True
print(9 >= 5) # prints True
```

The `==` operator checks for equality. If two numbers are the same it evaluates to the boolean value `True`. Otherwise `False`.

`!=` means not equals. It evaluates to `True` if the two things are *not* equal, otherwise `False`. We'll spend more time with the comparison operators soon, when we get to if statements.

## Variables

```python
a = 10
print(a) # prints 10
```

Taking a look at the above, hopefully it's intuitive enough coming from a math background. Let's talk about it anyway.

Here we are creating a variable `a` and we are *assigning* it a value of `10`. Variables are like buckets. We have a bucket with `a` painted on the side and we can store a value in it, in this case the integer `10`. We can then refer to the value stored in `a` and print it out. So far so good.

```python
a = 10
print(a + 5) # prints 15
```

The above should also follow from our understanding. `a` contains a value we can use in expressions like any other. What do you think the following will print out?

```python
a = 10
a = 20
print(a)
```

In math the above would be nonsense. `a` can't both equal `10` and `20`! Well in Python, as well as most (but not all!) programming languages variables are not constant. They can be reassigned. This is how we can read the above code:

- Create a variable `a`.
- Set `a` to `10`.
- Dump out the old value of `a` and replace it with `20`.
- Print the current value of `a`, which is `20`.

Let's test our understanding. What will the following print out?

```python
a = 10
b = 20
c = a + b
print(c)
```

It prints out `30`! The variable `c` is set to the result of `a` plus `b`. Ok, now for a tricky one.

```python
a = 10
b = 20
c = a + b
b = 5
print(c) # what does it print?
```

It still prints `30`. Why? Let's step through it.

- Create a variable `a` and set it to `10`.
- Create a variable `b` and set it to `20`.
- Create a variable `c` and set it to the result of `a + b`, which is `30`.
- Reassign `b` to equal `5`. Note that the value of `c` has not changed.
- Print `c`

In other words `c = a + b` is only true at the moment that line is executed. It is *not* necessarily true after that. `c` doesn't know or care where it got its values from, it only knows it contains a `30`. Make sense? Ok, one more concept.

```python
a = 10
a = a + 5
print(a) # what does it print?
```

## If

## While

## Interlude: Collatz Conjecture