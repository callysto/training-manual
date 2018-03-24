### 6. Software tools - Roll your own


*"Roll your own"* as in *"Roll your own cigarettes"* means as developers, we might prefer to do it all ourselves, as bright individuals who know what we want. 

The advantages of choosing our own software tools include:

- we can use the tools we think are best, or most familiar to us
- we can maintain our own system, not relying on an IT team
- we can run independent of the internet, not worried about connectivity
- we can choose tools that have more capabilities that the team's tools.

Some disadvantages include:

- our choice might not be compatible with the rest of the team
- our choice might not run in the finished project (eg. on the Callysto server)
- we have to do all the maintenance and conversions ourselves.

Nevertheless, if you want to roll your own, here are some choices that will help keep you consistent with the teams. 

#### Tools:

#### Browser:
Chrome, Firefor, Octave or Safari. Do not use Microsoft Explorer. You will need a capable  browser just to access the Jupyter hub. 

#### Jupyter Hub: 
Use the Anaconda distribution to install a Jupyter Server on your local machine, with Python 3 and R. [https://www.anaconda.com/](https://www.anaconda.com/)

Check for updates, keep it up to date. Note that you will need stick to this one distribution. For instance, Enthought Canopy is another possible distribution, but it does not play well with Anaconda. So just stick to the one distribution. 


A useful introduction to using a Jupyter hub, even on a local machine, is here:
[http://intro.syzygy.ca](http://intro.syzygy.ca)

#### Jupyter tree or lab:
You have a choice of running the Jupyter notebooks in the old *tree* format, or the newer *lab* format. Just change the local browser address from
```
http://localhost:8889/tree
to
http://localhost:8889/lab
```
or vice versa.

#### Operating system:
The Jupyter hub on your local machine is running on whatever system you machine is: Windows, MacOS, or Unix. By opening a terminal window in Jupyter (via the menu), you then have access to command lines for your machine. For instance, on a Mac OS it is essentially a bash terminal shell. Here you can run bash commands, compile C and Fortran code, run git, and so on. But of course you can do that directly from the Finder or a regular terminal window. 

#### Programming language:
Anaconda will automatically install Python and R. Make sure you use Python 3 (Python 2 is so old that no one should ever use it.) Other languages are possible, but for consistency across teams, our development will mainly be in Python 3.  

#### Code editors
The Jupyter hub has a built-in editor, both for regular text files and for your Jupyter notebooks. In the *lab* version, there are numerous improvements for making this a powerful and useful code editor. If you are looking for a more advanced editor for you machine, we recomment Atom for consistency across teams. [https://atom.io/](https://atom.io/)

#### Git and uploading/downloading files
The Jupyter hub allows you to upload and download individual directly. To use **git** you can either use a bash command directly in a notebook shell by prepending with an exclamation point
```
!git whatever...
```
or open a terminal shell and work directly in the bash shell. On Windows, you will need to install git -- good luck with that.