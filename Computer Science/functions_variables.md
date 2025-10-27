# Functions Variables

* [e.g. Python Functions](https://docs.python.org/3/library/functions.html)

**Code is Text**

* Visual Studio Code (VS Code)
* Any text editor

**hello.py**
```python
print('hello, world')
```

**bash**
```sh
enomoto@ubuntu:~/learning$ python hello.py
hello world
```

* **print()**: function
* **'hello, world'**: arguments

**Side Effect**

It can be visual, it can be audio.

**Bug**

Mistakes are referred to a term you might already know, which is that of a bug. A bug is a mistake in a program and they can take many forms.

```python
print('hello, world'
```

```sh
enomoto@ubuntu:~/learning$ python hello.py
SyntaxError: '(' was never closed
```

**Return Value**

Is the output of a function or method.

**Variables**

A variable is just a container for some value inside of a computers memory. A number, some text, even an image or video or more.

**Comments**

Comments are notes to yourself in your code. The program ignores your comments.

**Pseudocode**

Pseudocode is a nice way of structuring your to-do list,

```python
print(*objects, sep=' ', end='\n', file=None, flush=False)
```

**str**

[Python str](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)

```python
str.strip() # Remove whitespace from str
str.capitalize() # Return a copy of the string with its first character capitalized and the rest lowercased.
str.title() # Return a titlecased version of the string where words start with an uppercase character and the remaining characters are lowercase.
```

**Numeric Types**

[Python Numeric Types](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)

There are three distinct numeric types: integers, floating-point numbers, and complex numbers. In addition, Booleans are a subtype of integers. Integers have unlimited precision. 

* **int** [Python int](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
  * Whole numbers, no decimal point. Can be positive, negative, or zero.
* **float** [Python float](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
  * Numbers with decimal points. Can also be in exponential notation (e.g., 1e3 means 1000.0).
* **complex** [Python complex](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
  * Has a real and an imaginary part. Written as real + imagj (use j for √-1, like in engineering).

```python
numbers = [0, 2, 255, 256]

for number in numbers:
    number_bin = bin(number)
    number_lenght = number.bit_length()
    print(number, 'bin: ', number_bin, 'bits: ', number_lenght)

# 0 bin:  0b0 bits:  0
# 2 bin:  0b10 bits:  2
# 255 bin:  0b11111111 bits:  8
# 256 bin:  0b100000000 bits:  9
```
```python
import math

a = 5.3
b = 6.1

rounded = a+b
print(rounded)
print(math.ceil(rounded))
print(math.floor(rounded))

# 11.399999999999999
# 12
# 11
```

**def**

```python
def hello(name='World'):
    hello = f'Hello, {name}'
    print(hello)

hello()
hello('Matheus')

# Hello, World
# Hello, Matheus
```

**Bitwise Operations on Integer Types** [Python Bitwise](https://docs.python.org/3/library/stdtypes.html#bitwise-operations-on-integer-types)

Bitwise operations only make sense for integers. The result of bitwise operations is calculated as though carried out in two’s complement with an infinite number of sign bits.

**Graphical User Interface GUI**

allows users to interact with digital devices using visual elements like icons, buttons, and menus, rather than text commands. 

**Python - Cryptographic Services** [Python Crypto](https://docs.python.org/3/library/crypto.html)

The modules described in this chapter implement various algorithms of a cryptographic nature. They are available at the discretion of the installation.
