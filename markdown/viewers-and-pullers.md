# Viewers and Pullers



# nbviewer {#nbviewer}

This is a notebook viewer for Jupyter notebooks. It just seems to work, I don't really know how robust it is.

It can do animations in Python and in Julia, which is really impressive to me. The key is to have your .ipynb code available on a host like github, then paste its address into the box at this site:[http://nbviewer.jupyter.org/](http://nbviewer.jupyter.org/)

You can add links in Markdown to that code in the nbviewer directly, so the user only needs to click on the item. Simply type in the http address, as in these two examples:

Here is a Python plotting animation:[http://nbviewer.jupyter.org/github/mlamoureux/UsingSyzygy/blob/master/P\_AnimatedPlots.ipynb](http://nbviewer.jupyter.org/github/mlamoureux/UsingSyzygy/blob/master/P_AnimatedPlots.ipynb)

Here is a Julia animation \(from my Syzygy code\):[http://nbviewer.jupyter.org/github/mlamoureux/UsingSyzygy/blob/master/J\_Animation.ipynb](http://nbviewer.jupyter.org/github/mlamoureux/UsingSyzygy/blob/master/J_Animation.ipynb)

### NBGitPuller  {#nbgitpuller}

[NBGitPuller](https://github.com/data-8/nbgitpuller) is a very useful server extension which uses specially constructed URLs to allow students to be guided through the process of cloning out git repositories. As an example, an instructor might maintain a collection of notebooks for their class, which they will update and extend through the term. By giving a specially constructed URL to their students, each student will automatically be given their own copy of the files at the start of term and can keep it in sync \(without losing their changes\) as the term progresses.

We are in the process of rolling out this extension and making it available by default on all of our hubs so it may already be installed and activated on your syzygy.ca instance, or it will be soon. To use it, you need to construct URLs which specify the syzygy server you want to use and the repository you want to interact with. The URL will look something like



