### 14. Special topic: Making a script in Mac OS X

I find it useful to have a small command file in my Code folder, that I double click and it launches Jupyter for me, localized to the folder I want. A useful solution is to create a simple text file that has a list of terminal commands and turn that into a clickable application. 

The steps are as follows:

- Create a text file with a name like my_script.command
- Start it with a "shebang" command: #!/bin/bash
- list the terminal commands you want to run
- save the file
- set executive permission (i.e. in the terminal, run chmod +x /path/to/my_script.command)

For instance, here is the text file I used to customize my Jupyter launch:

```
#!/bin/bash
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
cd $DIR
jupyter notebook
```

The DIR variable is defined to point to the current directory where the launch command lives, which can be convention. The script then points to that directory before launching Jupyter.

I am sure there are similar methods in UNIX or Windows. 

