### 13. Best practices for code development

We will rely on Cybera personnel to guide us on this.

Some key ideas.

**Name spaces:** Python allows you to input many different packages of tools. It is fast but dangerous to import willy-nilly, like this
```
from numpy import *
```
This gives you access to functions like sin() and cos(), and many other functions, but the names may start to conflict if you load in too many packages like this.

Better to import using namespaces, like this
```
import numpy as np
import scipy as sp
import matplotlib as mpl
import matplotlib.pyplot as plt
```
So now, you would call np.sin() to get the sine function from numpy. Note that sc.sin() is another version of the sine function, fortunately they both do the same thing. 

We will extend this list to a standard list of imports and their abbreviations.

**Grouping files:** If your demo has many file associated to it (images,source code, etc.) it is best to keep them all organized into folder and subfolders, so users know what "package" to copy. 

**Repect the repo:** We have a repo to place the demos. There is some organization there, so repect it. Put stuff where they belong.