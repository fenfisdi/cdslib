# Contributing

Thank you for considering to contribute to our project 😊.

When contributing to this repository, please first discuss the change you
wish to make via _issue_ or _discussion_ with the owners of this repository
before making a change.

## Table of contents

- [Contributing](#contributing)
  - [Table of contents](#table-of-contents)
  - [How to make a clean pull request](#how-to-make-a-clean-pull-request)
  - [Code guidelines](#code-guidelines)
    - [Modules](#modules)
      - [Imports](#imports)
      - [Module names](#module-names)
      - [Maximum line length](#maximum-line-length)
      - [Modules size](#modules-size)
    - [Variables](#variables)
      - [Local variables](#local-variables)
      - [Global variables](#global-variables)
    - [Whitespace in expressions and statements](#whitespace-in-expressions-and-statements)
    - [Classes](#classes)
      - [Classes names](#classes-names)
      - [Classes size](#classes-size)
      - [Classes documentation](#classes-documentation)
    - [Methods and functions](#methods-and-functions)
      - [Methods and functions size](#methods-and-functions-size)
      - [Methods and functions parameters](#methods-and-functions-parameters)
      - [Methods and functions names](#methods-and-functions-names)
      - [Methods and functions documentation](#methods-and-functions-documentation)
    - [Documentation conventions](#documentation-conventions)
      - [Docstring format](#docstring-format)
  - [Naming Conventions](#naming-conventions)
    - [Camel Case: ```countElements```](#camel-case-countelements)
    - [Pascal Case: ```CountElements```](#pascal-case-countelements)
    - [Snake Case: ```count_elements```](#snake-case-count_elements)
    - [Kebab Case: ```count-elements```](#kebab-case-count-elements)

## How to make a clean pull request

Please follow the directions below:

- Create a personal fork of the project on **Github**.
- Clone the fork on your local machine. Your remote repo on **Github** is
  called origin.
- Add the original repository as a remote called upstream.
- If you created your fork a while ago be sure to pull upstream changes into
  your local repository.
- Create a new branch to work on! Branch from **dev** branch, never from
  **main**
- Run the tests to check if everything is ok.
- Implement/fix your feature, comment your code.
- Follow the [Code guidelines](##code-guidelines) of the project.
- Write or adapt tests as needed.
- Add or change the documentation as needed.
- Squash your commits into a single commit with git's interactive rebase.
  Create a new branch if necessary.
- Push your branch to your fork on **Github**, the remote origin.
- From your fork open a pull request in the correct branch. Target the
  project's **dev** branch.
- Once the pull request is approved and merged you can pull the changes
  from upstream to your local repo and delete your extra branch(es).
- And last but not least: Always write your commit messages in the present
  tense. Your commit message should describe what the commit,
  when applied, does to the code – not what you did to the code.

## Code guidelines

This section provides the guidelines we have defined for our Python projects.
This document tries to cover the major number of scenarios, nevertheless, this
document is alive and evolves through time.

### Modules

#### Imports

- ```imports``` must be done at the beginning of the module and just one import
  by line:

```python
  # Wrong
  import os, copy, time, functools
```

```python
  # Correct
  import os
  import copy
  import time
  import functools
```

- ```imports``` must be done following the next order:

1. Imports from **standard library**.
2. Imports from **third party libraries**.
3. Local imports from our library (these ones separated from the former ones using one blank line).

- At the end of the imports block, insert two blank lines:

```python
import os
import copy
import time
import functools
import numpy as np
import pandas as pd
# blank line
from my_module1 import my_class1
from my_module2 import my_function2
# blank line
# blank line
class MyClass:
```

- In the case of local modules imports which are inside folders, you must use
  relative paths (this is defined inside ```__init__.py``` file inside the
  folder).

#### Module names

Module names must be short and singular, with **Pascal Case** in order to
preserve readability (if you have any question about what Pascal Case means,
please review [Naming conventions](##naming-conventions) section).

#### Maximum line length

This project is governed by
[PEP8 guidelines](https://www.python.org/dev/peps/pep-0008) about the maximum
line length:

> Limit all lines to a maximum of 79 characters

#### Modules size

Modules must have a maximum size of 250 lines of code. In addition, each module
must have at most one class, and if it is a module of functions, then it must
have at most N functions without exceeding 250 lines of code.

### Variables

#### Local variables

Local variables must be placed at the begging of each scope and they must be
written in **Snake Case** with clear and intuitive names (if you have any
question about what Snake Case means, please review
[Naming conventions](##naming-conventions) section).

#### Global variables

Global variables must not be used in this project. Instead, consider to use
a parameters file or environment file.

### Whitespace in expressions and statements

Avoid extraneous whitespace in the following situations:

- Immediately inside parentheses, brackets or braces:

```python
# Correct:
spam(ham[1], {eggs: 2})
```

```python
# Wrong:
spam( ham[ 1 ], { eggs: 2 } )
```

- Between a trailing comma and a following close parenthesis:

```python
# Correct:
foo = (0,)
```

```python
# Wrong:
bar = (0, )
```

- Immediately before a comma, semicolon, or colon:

```python
# Correct:
if x == 4: print x, y; x, y = y, x
```

```python
# Wrong:
if x == 4 : print x , y ; x , y = y , x
```

However, in a slice the colon acts like a binary operator, and should have
equal amounts on either side (treating it as the operator with the lowest
priority). In an extended slice, both colons must have the same amount of
spacing applied. The only exception is when a slice parameter is omitted,
the space is omitted:

```python
# Correct:
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
```

```python
# Wrong:
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : upper]
ham[ : upper]
```

- Immediately before the open parenthesis that starts the argument list of a
  function call:

```python
# Correct:
spam(1)
```

```python
# Wrong:
spam (1)
```

- Immediately before the open parenthesis that starts an indexing or slicing:

```python
# Correct:
dct['key'] = lst[index]
```

```python
# Wrong:
dct ['key'] = lst [index]
```

- More than one space around an assignment (or other) operator to align it with
  another:

```python
# Correct:
x = 1
y = 2
long_variable = 3
```

```python
# Wrong:
x             = 1
y             = 2
long_variable = 3
```

### Classes

#### Classes names

Class name must decribe the class function, must be in singular and must be
written in **Pascal Case** (if you have any question about what Pascal Case
means, please review
[Naming conventions](##naming-conventions) section)

The class methods must be named in a clear manner and following the
[PEP8 guidelines](https://www.python.org/dev/peps/pep-0008). The most important
thing, is that their name must be intuitive enough to infer their role in the
class.

#### Classes size

Classes must not exceed 250 lines of code.

#### Classes documentation

All classes and their corresponding methods must have their own documentation.
Please refer to [Documentation conventions](###documentation-conventions)
section.

### Methods and functions

Methods and functions must be precise and have very specific functionalities.
In addition, inside functions there must not be calls to functions defined
after the function where they are invoked.

#### Methods and functions size

Methods and functions must not exceed 20 lines of code, and if they do, then it
should be better to create new functions to reduce the scope of original ones
or to use refactoring techniques.

#### Methods and functions parameters

Methods and functions must have at most 5 parameters. In case that the function
exceeds 5 parameters, then they should be passaed using _args_ or _kwargs_, or
to use refactoring techniques. The parameters names must follow variables names
guidelines.

#### Methods and functions names

Methods and functions must be named in such a way that their purpose or
behavior is clear and they must be written using **Snake Case** (if you have
any question about what Snake Case means, please review
[Naming conventions](##naming-conventions) section).

#### Methods and functions documentation

All methods and functions must be properly documented, specifying the type of
the parameters, their functionality and their return (if it has one).
Please refer to [Documentation conventions](###documentation-conventions)
section.

### Documentation conventions

The documentation of this project is developed using the
[Sphinx framework](www.sphinx-doc.org).
All files related to it can be accessed in the corresponding `~/docs`
directory.

#### Docstring format

In this project we use the [NumPy-SciPy docstrings](https://numpydoc.readthedocs.io/en/latest/format.html)
format. In any case, the docstring must contain at least the first-line general
description. Depending on the object to be documented, it must also include:

- *Functions and methods*:

  - List of parameters with the corresponding data types
  - Return data type and description

- *Classes*:

  - List of attributes with descriptions
  - All methods must be appropiately documented

A good external reference to start with is
[Documenting Python Code: A Complete Guide](https://realpython.com/documenting-python-code/).

## Naming Conventions

### Camel Case: ```countElements```

The Camel Case notation combines the words directly, without using any symbol,
establishing that the first letter of each word is in uppercase except for the
first word, with the rest of the letters in lowercase.

Examples:

```countWords```

```increaseDifficultyLevel```

### Pascal Case: ```CountElements```

The Pascal Case notation combines the words directly, without using any
symbols, establishing that the first letter of each word is in uppercase
without exceptions, the rest of the letters being in lowercase.

Examples:

```CountWords```

```IncreaseDifficultyLevel```

### Snake Case: ```count_elements```

The Snake Case notation combines the words using an underscore _ as a nexus.
There are two versions of this notation, one in which all the letters are
lowercase and one in which all the letters are lowercase.

Examples:

```count_words```

```increase_difficulty_level```

### Kebab Case: ```count-elements```

Kebab Case notation combines the words using a hyphen - as a nexus.
The letters will all be lowercase.

Examples:

```count-words```

```increase-difficulty-level```
