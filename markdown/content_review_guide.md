# Content Reviewer's Guide

This guide is intended for use by anyone who will be reviewing the content of any notebooks developed for the Callysto project. Certainly, if you're a developer for the Callysto project, knowing how your content will be assessed in advance will likely be helpful as well.



## Review Process
We have outlined a standard review process below.

### Does the Notebook Adhere to the Style Guide?
First and foremost, check to see if the notebook itself adheres to the Callysto style guide available [here](notebook-format.md), or [here](notebook-template.md) for a condensed version. If a notebook doesn't contain those elements (or doesn't have a good reason to not contain those elements), that notebook should not pass review until those requirements are satisfied.


### Content
The following are areas to pay attention to when reviewing a notebook for Callysto
1. Has the document been spell checked and does it use proper grammar?
    - Does the notebook use full sentences, paragraphs and punctuation?  
1. Does the notebook keep the target audience in mind?
   - Is the grammar, narrative, examples, questions and exercises appropriate for the intended audience?
   - If at any point you as a reviewer are left confused by a sentence/explanation, that sentence/explanation needs work.
1. Does the notebook make sense?
   - Does the notebook have a coherent narrative?
   - Is the lesson/objective of the notebook obvious?
   - Is the notebook well organized?
      - Do sections lead well into each other - is there some logic connecting them?
   - Is the spelling and grammar correct/appropriate for the audience the notebook is intended for?
1. Does the notebook contain some sort of interactivity?
   - Widgets, animations, filling in segments of code etc.
1. Does the notebook demonstrate computational thinking in a way that is independent of understanding the underlying code?
   - See [computational thinking](computational_thinking.md)
   - Not applicable for notebooks where teaching the student to code is the lesson.
1. Does the notebook use an open data source to assist with the development of the notebook narrative and examples?
   - If you feel there is an open data source that could assist with the lesson, please let the developer know so that they may incorporate it
   - This may not be applicable in many cases.
   - Don't suggest incorporation of open data simply for the sake of incorporating open data.
6. Does the notebook complete its curriculum objective?


If the notebook you're reviewing has problems with any of the above, it will be important that you're clear with the developer as to what the issue is, and any suggestions you have for fixing those problems. Don't just tell the developer something like "your notebook is inappropriate for the intended audience" without also telling them _why_ and any suggestions you may have to fix it. Getting the developer to fix these issues will be considerably more efficient if they're given a starting point/reasons why they need to make changes.


### More Specific Basic Aesthetic Points
We also want our notebooks to "look good". There is certainly no expectation that each notebook should appear as if it was masterfully constructed by a graphic designer, but little stylistic things are important. Below is a list of common stylistic issues to watch out for.

1. Does the notebook use consistent title formatting?
   - Is the title of the notebook created with `# Title`?
   - Are main sections denoted with `## Section Title`?
   - Are subsections denoted with extra pound signs?
   - Is this done consistently?
1. Images
    - Do images possess a caption/is their relevance explained somewhere in adjacent text?
    - Does their placement make sense?
    - Is the image/font within large enough to read?
1. Graphs
    - Are all axis labelled?
      - With units (where applicable)?
    - Is the font large enough to read at a glance?
    - Is there a legend (where applicable)?
1. Tables
    - If the notebook contains data tables, is the column alignment consistent?
    - Is the table cut off due to the width of the window?
    - Do the column names make sense?
    - Do the column names contain units (where applicable)?
1. In line code/code blocks
    - Is inline code/variable references in the main body contained within back tics ( \` ) such that it renders as `variable`, so that it is distinguishable in the main body?
    - Are blocks of code to be discussed in triple back ticks ( \`\`\` ) such that they render similar to:
      ```python
      while True:
        # Infinite loops are okay in markdown
        print('''
              By adhering to basic style principles
              notebooks will be much more aesthetically pleasing.
              ''')
      ```
1. Mathematical typesetting
    - Are inline variables surrounded in dollar signs (for example`$x$`), such that it renders as $x$?
    - Are large expressions given their own line either with `$$ big math expression $$` or
     `\begin{equation}  
     big math expression
     \end{equation}`?
     - For example, something large and horrible like $$\left[-\frac{\hbar^2}{2m}\nabla^2+V(\vec r) + \int \frac{e^2n_\mathrm{s}\left(\vec r'\right)}{\left|\vec r-\vec r'\right|} \,{\mathrm d}^3r' + V_\mathrm{XC}[n_\mathrm{s}(\vec r)](\vec r)\right] \varphi_i(\vec r) = \varepsilon_i \varphi_i(\vec r)$$ should never appear in-line like this, and should be put in the proper equation environment.
     - If an equation is referenced in the discussion, is the equation numbered?
1. Coloring/fonts
    - Are any custom fonts/colors readable?
1. External links
    - Are they hidden with something like `[link to display](longlonglongwebsite.com)`?
         - Does the link work?
1. Citations
     - Are citations surrounded with " and start with > (example >"Citation")?

In the case of these stylistic concerns, any fixes should be easy and straightforward to communicate to the developer. These are certainly tedious points, but if we're consistent with enforcing these, our notebooks will be stylistically similar between developers, and be pleasant on the eye.
