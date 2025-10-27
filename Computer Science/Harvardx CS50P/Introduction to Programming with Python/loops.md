# Loops

**Loop**

A loop is a way to repeat code multiple times — automatically.

**while**[Python while](https://docs.python.org/3/reference/compound_stmts.html#while)

The while statement is used for repeated execution as long as an expression is true:

**for**[Python for](https://docs.python.org/pt-br/3/reference/compound_stmts.html#for)

The for statement is used to iterate over the elements of a sequence (such as a string, tuple or list) or other iterable object:

**break**[Python break](https://docs.python.org/3/reference/simple_stmts.html#break)

break may only occur syntactically nested in a for or while loop, but not nested in a function or class definition within that loop.

**continue**[Python continue](https://docs.python.org/3/reference/simple_stmts.html#continue)

continue may only occur syntactically nested in a for or while loop, but not nested in a function or class definition within that loop. It continues with the next cycle of the nearest enclosing loop.

```python
# Using a for loop
for i in range(10):
    if i % 2 == 0:
        continue  # Skip even numbers
    if i == 7:
        break     # Stop the loop when i is 7
    print("For loop:", i)

While loop: 1
While loop: 3
While loop: 5
```
```python
# Using a while loop
i = 0
while i < 10:
    if i % 2 == 0:
        i += 1
        continue  # Skip even numbers
    if i == 7:
        break     # Stop the loop when i is 7
    print("While loop:", i)
    i += 1

While loop: 1
While loop: 3
While loop: 5
```
