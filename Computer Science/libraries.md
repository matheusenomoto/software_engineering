# Libraries

**modules** [Python modules](https://docs.python.org/3/tutorial/modules.html)

A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. Within a module, the module’s name (as a string) is available as the value of the global variable

**import** [Python import](https://docs.python.org/3/reference/import.html)

Python code in one module gains access to the code in another module by the process of importing it. The import statement is the most common way of invoking the import machinery, but it is not the only way.

**random** [Python random](https://docs.python.org/3/library/random.html)

This module implements pseudo-random number generators for various distributions.

**statistics** [Python statistics](https://docs.python.org/3/library/statistics.html)

This module provides functions for calculating mathematical statistics of numeric (Real-valued) data.

**sys** [Python sys](https://docs.python.org/3/library/sys.html)

This module provides access to some variables used or maintained by the interpreter and to functions that interact strongly with the interpreter. It is always available. Unless explicitly noted otherwise, all variables are read-only.

```python
import sys

print("hello, my name is:", sys.argv[0])
```

**sys.argv** [Python sys.argv](https://docs.python.org/3/library/sys.html#sys.argv)

The list of command line arguments passed to a Python script. argv[0] is the script name (it is operating system dependent whether this is a full pathname or not). If the command was executed using the -c command line option to the interpreter, argv[0] is set to the string '-c'. If no script name was passed to the Python interpreter, argv[0] is the empty string.

**command-line arguments** [Python command-line arguments](https://docs.python.org/3/using/cmdline.html)

The CPython interpreter scans the command line and the environment for various settings.

**json** [Python json](https://docs.python.org/3/library/json.html)

JSON (JavaScript Object Notation), is a lightweight data interchange format inspired by JavaScript object literal syntax (although it is not a strict subset of JavaScript).

**requests** [Python requests](https://requests.readthedocs.io/en/latest/user/quickstart/)

An elegant and simple HTTP library for Python, built for human beings.
