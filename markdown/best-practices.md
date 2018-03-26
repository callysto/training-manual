### 13. Best practices for code development

#### Inherited Best Practices

We should attempt to follow the coding practices of the Python community as closely as possible. The folks who've taken the time to develop them have thought much more than any of us about what makes Python code easier to read. Assuming the majority of Python code outside Callysto also follows the community's style guide, this will also make outside resources easier to use.

[PEP 8](http://pep8.org) is considered the de-facto style guide of the Python community. Note that one of the first things it talks about is the importance of being willing to break the rules. This may be of special importance to this project, as we are not looking to teach Python so much as teach computational thinking, and sometimes what is natural and idiomatic in a particular language is just plain weird compared to the majority of other languages. Still, we should think hard about deviations from PEP 8 and note them here.

#### Following What's Already There

A simple, but effective, way to make sure you're following these coding guidelines is to first take a look at existing content and follow the style of that. If you notice something about the style that seems odd to you, that may be a good time to review these guidelines and/or the underlying PEP 8 guidelines. In doing this, you may find that something in the repository isn't following these guidelines. 

This will almost certainly happen with many people contributing code and as certain coding practices are modified. This guide won't assume the way your team is working. You may have an issue log that's kept to address later, you may have a single person in charge of the notebook that you inform, or if there's an appropriate Git process in place, you may be able to submit your own change and have it merged.

#### Making Changes

Anyone should feel comfortable with suggesting changes to these best practices, as we will all likely discover some important and necessary ones along the way. Conforming to PEP 8 when there's not a compelling reason to deviate will help avoid purely stylistic arguments. As the project gains momentum and more code, changes will be harder, so the sooner we discover any major changes we want to make, the better.

Note: If you're used to another language or following another style guide, it's natural for some things to feel awkward. This, in itself, isn't a great argument for a change to these guidelines. It's likely different things will feel awkward for everyone. When suggesting a change, please make sure to consider the costs and benefits of making it. The better the argument, the more likely everyone will agree.

#### Consistent Name Spaces

When a module is imported by Python, the functions within it still need to be prefixed with the module's name. So, for example, a module called "fizz" with a function called "buzz" would be used in the following way:

```python
import fizz

fizz.buzz()
```

This is called namespacing and helps to avoid conflicts when functions are named similarly. While namespacing helps avoid conflicts, it can also make Python code harder to read when overused and when the module names themselves are long. There are variations of the `import` statement that can deal with these cases.

A common variation used with certain popular packages is to create a shorter alias. For example, the `numpy` package is often imported like this:

```python
import numpy as np

x = np.array([2,3,1,0])
```

Aliasing modules like this is good practice when those modules are aliased in the same way by the community surrounding them. Numpy is a great example of this. You should avoid defining your own aliases. If there is a module without a community defined alias that you feel strongly should have one within our notebooks, make sure to bring it up with your fellow developers (team lead?). If it is adopted, it will be something we'll want to do consistently in other modules within the project.

Functions (or submodules) that are used very often within a notebook can be specifically imported without a namespace:

```python
from os import path
from math import pi

some_path = path.join("folder1", "folder2", "file.txt")
radius = 5
area = pi * radius**2
```

Two other variations worth noting:

```python
from math import cos as cosine
```

This should probably be avoided in most cases, especially with standard Python libraries. The standard names will be easy to search for help on outside of Callysto. The aliases you might make up won't. However, there are cases where this may be useful. For example, if you find a rather obscure library with poorly named functions that nevertheless has one function (also poorly named) that's really, really useful, importing it this way would likely improve the readability of your code.

```python
from math import *
```

As noted in PEP 8, you really shouldn't be doing this, as it's really easy to polute your current namespace and wind up with weird bugs due to unintended function replacements. PEP 8 notes some exceptions, and there's one exception noted below for our purposes.

##### Popular Aliases

Here's a list of packages that we know of along with the aliases you should use (based on aliases used by the communities surrounding them) when importing and referencing them.

If there's a module that uses a common alias and is missing from this list, please add it.

```
import numpy as np
import scipy as sp
import matplotlib as mpl
import matplotlib.pyplot as plt
import pandas as pd
```

#### Managing Complexity

When developing a module, spend some time considering what aspects of computational thinking you're actually trying to demonstrate and whether or not you can assume any prerequisite knowledge in various programming concepts.

Whenever there is a need to reduce complexity without also reducing functionality (i.e. you want to show a fancy plot but not go over all of the necessary knowledge to produce that plot), consider extracting that complexity into a function in a separate Python file that is included alongside the notebook:

```
/some_folder/
  My Awesome Notebook.ipynb
  my_awesome_support.py
```

Example **my_awesome_support.py**:

```python
import os
import numpy as np
import sys
import hashlib

def complex_fizz():
  md5 = hashlib.md5()
  for x in ["buzz", "fizz", "buzz"]:
    md5.update(x.encode("utf-8"))
  return md5.hexdigest()
```

Example **My Awesome Notebook.ipynb**:

```python
from my_awesome_support import *
```

You may note that the use of `import *` is discouraged in PEP 8. In this case, we really do want to grab everything in the file. The functions we've defined in it are specifically for this notebook (so we're not worried about them clashing with existing functions), and we're bringing in imports, such as `os` and `numpy as np` that are already namespaced.

There likely won't be a need for more than one support file per notebook (or any at all), so we'll delay talking about more complex setups until they're needed. However, if we find we're extracting the same functions over and over again, this might be a sign that a separate package should be maintained.

Note that an additional benefit of maintaining a convention of a similarly named file alongside the notebook file in the same folder is that it is easy to find the code that we've chosen to hide in this way for anyone who's curious.

#### Folders

If your demo has many file associated to it (images,source code, etc.) it is best to keep them all organized into folder and subfolders, so users know what "package" to copy.

#### Keeping it Simple

Consider the following example of two ways of creating an array of integers:

```python
x = [1,2,3,4]

import numpy as np
x = np.array([1,2,3,4])
```

This is an area where our experience with Python and especially some of the more popular packages may work against us. There are various optimizations and additions to arrays that make the use of `np.array` to create them worth the extra typing and effort to read. However, if you've never encountered an array before, this makes it much harder to understand what the code is doing.

For Callysto, we should prefer the first, simpler way of initializing an array. An added benefit (and something to also consider) is that this is also a common way of initializing an array in *many* languages.

Note that we can always convert a regular array into a numpy array internally if it is needed for some interesting package we want to use, even if this is less efficient, it allows us to hide the complexity up front.

List comprehensions (i.e. `x = [a for a in y]`) are generally considered "good Python" by the community. However, while many languages have mapping functions that serve a similar purpose, the syntax for list comprehensions is pretty unique to Python. When at all possible, you should use classic for-loops, even if you end up with less concise code.

#### Comments and readability

PEP 8 has some great guidelines for comments in general. These guidelines are especially useful in any supporting python files.

In the notebooks themselves, also consider the other tool at your disposal: the markdown blocks themselves. If you've explained what you're doing in a code block in the markdown above it, there's no need to repeat that explanation in an actual code comment. With longer pieces of code, when you find yourself about to write a comment, consider whether it would be better to actually create another markdown block and continue your code below that. 

Rule of thumb: the more important a particular section of code is to understand, the more likely it should be its own code block.

Good variable names, abstractions, modularization, and data structures are just as important for readability as comments. Which is easier to understand?

```python
nums = range(0,10)

x = 0 # even sum
y = 0 # odd sum

for num in nums:
  # check if the number is even
  if num % 2 == 0:
    x = x + num
  else:
    y = y + num
```

Or:

```python
nums = range(0,10)

even_sum = 0
odd_sum = 0

def is_even(x):
  return x % 2 == 0

for num in nums:
  if is_even(num):
    even_sum = even_sum + num
  else:
    odd_sum = odd_sum + num
```

The `is_even` function may be overkill once you get used to seeing the `%` operator enough. Combined with more appropriately named variables, however, it makes it much easier to follow what the code is doing. Once someone gets comfortable with the `filter` and `sum` functions, which are nice abstractions for certain operations over lists (and assuming we also define an `is_odd` function), we can write even more readable code:

```python
even_nums = filter(is_even, nums)
odd_nums = filter(is_odd, nums)
even_sum = sum(even_nums)
odd_sum = sum(odd_nums)
```

However, it's important to note that passing functions into functions is a more advanced programming concept, and the improved readability here relies heavily on the understanding of this concept.

#### Packages

Be careful when installing Python packages. We don't want to have any install requirements for end users of these notebooks, so if there's a package you really need, this will eventually have to be communicated to the maintainers of hub.callysto.ca. Keep a list of any packages you install this way (should we spell out a specific name/location?) and consider how much you really need it. How much code would you have to write in a supporting python file to do what the library is doing for you? Could you copy the necessary functions as supporting Python files (maintaining any necessary attributions and/or licensing requirements).