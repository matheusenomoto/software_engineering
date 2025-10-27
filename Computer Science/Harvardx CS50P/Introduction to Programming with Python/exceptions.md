# Exceptions

**SyntaxError** [Python SyntaxError](https://docs.python.org/3/library/exceptions.html#SyntaxError)

A syntax error is a problem that you've got to go back into your code. Raised when the parser encounters a syntax error. This may occur in an import statement, in a call to the built-in functions compile(), exec(), or eval(), or when reading the initial script or standard input (also interactively).

**ValueError**[Python ValueError](https://docs.python.org/3/library/exceptions.html#ValueError)

```python
x = int(input("What's x? "))
    print(f"X is {x}")

# What's x? car
# ValueError: invalid literal for int() with base 10: 'car'
```

**try and except**

[Python try](https://docs.python.org/3/reference/compound_stmts.html#the-try-statement)The try statement specifies exception handlers and/or cleanup code for a group of statements.

[Python except](https://docs.python.org/3/reference/compound_stmts.html#except) - The except clause(s) specify one or more exception handlers. When no exception occurs in the try clause, no exception handler is executed.

```python
try:
    x = int(input("What's x? "))
    print(f"X is {x}")
except ValueError:
    print(f"x is not an integer")

# What's x? cars
# x is not an integer
```


**NameError** [Python NameError](https://docs.python.org/3/library/exceptions.html#NameError)

Raised when a local or global name is not found. This applies only to unqualified names. The associated value is an error message that includes the name that could not be foun

```python
try:
    x = int(input("What's x? "))
    print(f"X is {x}")
except ValueError:
    print(f"x is not an integer")

print(x)

# What's x? cars
# x is not an integer
# NameError: name 'x' is not defined
```

**else**

The try … except statement has an optional else clause, which, when present, must follow all except clauses. It is useful for code that must be executed if the try clause does not raise an exception. 

```python
try:
    x = int(input("What's x? "))
except ValueError:
    print(f"x is not an integer")
else:
    print(x)

# What's x? cars
# x is not an integer
```

```python
while True:
    try:
        x = int(input("What's x? "))
    except ValueError:
        print(f"x is not an integer")
    else:
        break

print(f"x is {x}")
```

```sh
What's x? a
x is not an integer
What's x? 1.2
x is not an integer
What's x? 5
x is 5
```

Break is used to break out of loops. But it turns out that return is sort of stronger than break. It will not only break you out of a loop. It will also return a value for you.

**pass** [Python pass](https://docs.python.org/3/reference/simple_stmts.html#pass)

Is a null operation — when it is executed, nothing happens. It Is useful as a placeholder when a statement is required syntactically, but no code needs to be executed.

**raise** [Python raise](https://docs.python.org/3/reference/simple_stmts.html#raise)

If no expressions are present, raise re-raises the exception that is currently being handled, which is also known as the active exception. If there isn’t currently an active exception, a RuntimeError exception is raised indicating that this is an error.
