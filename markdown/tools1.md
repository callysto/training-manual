### 5. Software tools - Eat your own dogfood

"Eat your own dogfood" means that, as developers, we should be using the same tools that we are developing for our clients. (The slogan originates with Microsoft.) 

The tools we want teachers and students to use are:

- Jupyter notebooks
- accessed over a remote server on the web
- with Python, Markdown, and html/javascript for coding and presentaion
- and repositories on Github.

The advantages of using our our own tools are manifold:

- the content your write will work as expected for the clients
- the performance you see will be the same for the client
- the developer teams will have a uniform environment to create in
- the IT team has only one uniform plaform to maintain for the many teams.

Some disadvantages include:

- developers need constant, high quality internet access
- the IT teams needs to keep the server up and running with high reliability
- some of the cool things you can do on your own laptop may break on the server-client model.

#### Tools:

#### Browser:
Chrome, Firefor, Octave or Safari. Do not use Microsoft Explorer. You will need a capable  internet browser to access all the tools online. 

#### Jupyter Hub: 
We use the Callysto Jupyter server running remotely on Cybera infrastructure, accessible here: [https://hub.callysto.ca](https://hub.callysto.ca)  

Just log in with your browser, using your Google ID. Note that each ID gets a separate space on the server, with about one Gigabyte of storage space for files, and one Gigabyte of RAM for operation. 

A useful introduction to using a Jupyter hub is here:
[http://intro.syzygy.ca](http://intro.syzygy.ca)

#### Jupyter tree or lab:
You have a choice of running the Jupyter notebooks in the old *tree* format, or the newer *lab* format. Just change the browser address from
```
https://hub.callysto.ca/jupyter/user/myname/tree
to
https://hub.callysto.ca/jupyter/user/myname/lab
```
where *myname* is your Google account name.

#### Operating system:
The server is running Unix. By opening a terminal window in Jupyter (via the menu), you can access your personal virtual machine that is a full blown Unix system for you. Here you can run bash commands, compile C and Fortran code, run git, and so on. 

#### Programming language:
We have Python 3 and R available on the server, with many of the standard packages already pre-installed. Other languages are possible, but for consistency across teams, our development will mainly be in Python 3.  

#### Code editors
The Jupyter hub has a built-in editor, both for regular text files and for your Jupyter notebooks. In the *lab* version, there are numerous improvements for making this a powerful and useful code editor. If you must, you can use **emacs** or **vim** through a terminal window. 

#### Git and uploading/downloading files
The Jupyter hub allows you to upload and download individual files between your local computer and the server. To use **git** you can either use a bash command directly in a notebook shell by prepending with an exclamation point
```
!git whatever...
```
or open a terminal shell and work directly in the bash shell.

