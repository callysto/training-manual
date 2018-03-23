
### 14. Special topics: YouTube Video

With just a couple of lines, you can embed a clickable YouTube video link into your Jupyter notebook:

<iframe
    width="600"
    height="500"
    src="https://www.youtube.com/embed/kthi--SH2Nk"
    frameborder="0"
    allowfullscreen>
</iframe>



The Python code looks like this:
```
from IPython.display import YouTubeVideo
YouTubeVideo('kthi--SH2Nk') 
```

You can also insert your own mp4 videos into the notebook. such as this example: 

<iframe
    width="300"
    height="300"
    src="/assets/knot.mp4"
    type="video/mp4"
    frameborder="0"
    allowfullscreen> 
</iframe>


With the keyword *controls autoplay loop* we get a video with a slider control, that starts playing automatically, and loops continuously. The Python code looks like this:

```
from IPython.display import HTML
HTML("""
<video width="320" height="240" controls autoplay loop>
  <source src="/assets/knot.mp4" type="video/mp4">
</video>
""")
```





<video width="320" height="240" controls autoplay loop>
<source src="/assets/knot.mp4" type="video/mp4">
</video>


