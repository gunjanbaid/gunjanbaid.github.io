---
layout: post
title:  "JupyterDayPhilly"
date:   2017-05-29
categories: jekyll update
comments: true
---

![presentation](/assets/images/JupyterDayPhilly.jpg)

<br>
Two weeks ago, I attended [JupyterDayPhilly: Transformative Teaching with the Jupyter Notebook](https://jupyterday.blogs.brynmawr.edu/) 
at Bryn Mawr College in Bryn Mawr, PA. The two-day conference focused on how Jupyter notebooks can be used to teach in a way that promotes equality and diversity in STEM. 
I had the chance to speak about UC Berkeley's [Data Science Education Program](http://data.berkeley.edu/education) 
and also hear speakers from academia and industry. 
I wrote this post to share my experience and highlight some of the cool presentations I saw.


## 1. My presentation

I gave a talk (after missing a connecting flight and traveling to four airports in one night) 
titled *Data Science at UC Berkeley: 2000 undergraduates, 50 majors, no command line*.
I started with an overview of the data science program and courses at UC Berkeley and then covered
some of the tools used in the lower division courses (Data 8 + connectors). 
You can check out my slides below or [here](https://docs.google.com/presentation/d/1oCKSRB_goWeRGpD1eWbGBGooM5Jla_0O573CdnwMo24/edit?usp=sharing). 

<iframe src="https://docs.google.com/presentation/d/1oCKSRB_goWeRGpD1eWbGBGooM5Jla_0O573CdnwMo24/embed?start=false&loop=false&delayms=3000" frameborder="0" width="480" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<br>

## 2. Some cool tools

### 2.1 Orioles

[Example](https://www.oreilly.com/learning/regex-golf-with-peter-norvig)

Andrew Odewahn, the CTO of O'Reilly Media, spoke about the work O'Reilly is doing to produce 
digital content for learning. While many people are best familiar with O'Reilly books 
(the ones with black and white animal drawings on the covers), 
[orioles](https://www.safaribooksonline.com/oriole/) are a new digital learning format that the company has developed. 
Orioles use Jupyter notebooks to create a web page that contains a video tutorial, text explanations, and code examples. 
As the video is playing, the page automatically scrolls to the corresponding text and code sections, 
creating an immediately interactive video tutorial.

### 2.2 Jupyter Magic

Doug Blank, a professor at Bryn Mawr, spoke about some Jupyter magic commands he has developed. 
There are many Jupyter magic commands start with `%` or `%%` and have various functionalities.
Some are [built-in](http://ipython.readthedocs.io/en/stable/interactive/magics.html) 
and [others](https://github.com/Calysto/metakernel/tree/master/metakernel/magics) can be downloaded. 
A commonly used one is `% matplotlib inline`, which is used to display figures properly in the notebooks. 
Below are two magic commands that I found interesting.

#### `% activity`

[Example](https://athena.brynmawr.edu/jupyter/hub/dblank/public/Activity%20Magic.ipynb), 
[Source](https://github.com/Calysto/metakernel/blob/master/metakernel/magics/activity_magic.py)

Activity magic allows instructors to embed polls or quiz questions in the notebooks. 
These can be used in classrooms as clicker-style questions.
Students can answer the questions present in a notebook and also see a graph of the results from 
all student responses. Student responses are written to a file that instructors can collect and parse.

Given the setup of  Berkeley's data science JupyterHubs (no shared filesystem), this command cannot 
be used on those hubs directly. However, I still thought it was worth sharing.

#### `%% tutor`

[Example](https://athena.brynmawr.edu/jupyter/hub/dblank/public/Examples/Tutor%20Magic%20in%20IPython.ipynb), 
[Source](https://github.com/Calysto/metakernel/blob/master/metakernel/magics/tutor_magic.py)

Tutor magic allows you to embed [Python Tutor](http://www.pythontutor.com/) diagrams for a code cell 
directly in the notebook with very little work.
 

### 2.3 Notebook Slides

[Example](http://www.slideviper.oquanta.info/tutorial/slideshow_tutorial_slides.html#/)

Many of the presenters at JupyterDayPhilly used Jupyter notebooks to create their slides. 
[nbconvert](https://github.com/jupyter/nbconvert) allows you to convert a Jupyter notebook into other formats (html, markdown, etc.).
You can also use nbconvert to convert your notebook into a slideshow!

To do so, open up the notebook and then click *View –> Cell Toolbar –> Slideshow*. 
You will then see a dropdown called *Slide Type* for each cell in the notebook.
You can use this dropdown to format each cell into a slide, subslide, etc. 

After formatting the notebook cells, you can create the slideshow by running the following command. 

```
jupyter nbconvert <notebook name>.ipynb --to slides --reveal-prefix "https://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.1.0"
```

If the above command is not generating the slideshow correctly, the URL after *--reveal-prefix* may be out of date. 
You can try checking [this file](https://github.com/jupyter/nbconvert/blob/master/nbconvert/postprocessors/serve.py) for an updated URL.

## 3. Courses

[Examples](https://jupyterday.blogs.brynmawr.edu/schedule/)

Besdies tools, several instructors at the conference explained how they using Jupyter notebooks in their classrooms. 
Instructors from universities in and out of the country presented the materials they use in their courses. 
These courses covered a broad range of fields, including biology, physics, and math. 
Having strongly disliked Mastering Physics assignments in physics courses at Berkeley,
I appreciated the interactive nature of the physics materials in particular. You can find presentation slides
and related materials on the page linked above.

## 4. Final Thoughts

Thank you to DSEP and the organizers of JupyterDayPhilly at Bryn Mawr for the opportunity to attend this conference.
I enjoyed meeting the Jupyter community and look forward to seeing both familiar and new faces at 
[JupyterCon](https://conferences.oreilly.com/jupyter/jup-ny) this August.

I encourage anyone reading this post to check out not just the tools mentioned above, 
but the many other that exist. [CoCalc]() (formerly known as SageMathCloud) was another resource 
mentioned at the conference, but I didn't have the chance to use it thoroughly.

Finally, my presentation at JupyterDayPhilly was my first conference talk and this is my first blog post. 
If you have any comments on either, feel free to post below.
I would love to hear thoughts/suggestions. Thanks for reading!

<br>

{% include disqus.html %}