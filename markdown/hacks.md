### 14. Special topic: Hacks to input html code and Javascript

The Jupyter server and iPython can easily display html code that is in a file. The commands for this are simply to import IFrame and then call it with the file name, and dimensions for the display:

```
from IPython.display import IFrame
IFrame('mb.html',500,500)
```

However, the Jupyter server is sometimes very cautious about Javascript code embedded in the html file, and will attempt to 'scrub' it, removing what it thinks is dangerous. A simple hack to avoid this is to re-name the file something other than .html, read it in, and write it again with the .hmtl suffix. Somehow this convinces Jupyter that the file is safe. Which is crazy, right?

Here is an example, reading in a file called "MovingBalls.template" and then saving it under a new name.

```
with open('MovingBalls.template','r') as f:
    s=f.read()
    with open('mb.html','w') as g:
        g.write(s)
    
IFrame('mb.html',500,500)

```