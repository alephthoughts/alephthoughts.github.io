---
layout: post
title: Publication ready Jupyter Notebooks
image: /img/python.png
tags: [dev, data science, jupyter, python]
---
Documenting your work is an integral part of your development but if you are someone like me and you have to share your work with different set of technical and non-technical audience, you probably go an extra mile to create separate versions of the same results, one with code for your peers, and one for the business stakeholders who may find the code scary or distracting to say the least. [The Jupyter Notebook](https://jupyter.org/) makes my life so much easier for the data analysis related work. Although jupyter notebook supports a variety of programming languages like [Julia](https://julialang.org/), [Python](python.org) and [R](https://www.r-project.org/) for live code and visualisations, alongwith [Markdown](https://en.wikipedia.org/wiki/Markdown), [HTML](https://en.wikipedia.org/wiki/HTML) and others for narrative text, in this post, we will see an example with python code.

### Installing Required Packages
Assuming you already have jupyter and python installed on your systems, you need to install the following packages additionally:

#### [nbconvert](https://github.com/jupyter/nbconvert)
The nbconvert tools utilises [Jinja](http://jinja.pocoo.org/) templates to convert your jupyter notebooks to various document formats such as HTML, LaTeX, PDF, Reveal JS, Markdown, ReStructured Text (rst) and executable script.
You can install nbconvert using either of the commands depending on your python package manager:

`pip install nbconvert`<br>
`conda install -c anaconda nbconvert`


To convert the notebook to the desired output format use the following command structure:

`$ jupyter nbconvert --to <output format> <input notebook>`


#### [Hide_Code](https://github.com/kirbs-/hide_code)
Hide_Code is an extension for your jupyter notebook, which allows you to selectively hide code, prompts and outputs in the jupyter notebook. It also enables these notebooks to be exported to HTML, LaTeX and PDF. Once hide_code is installed on your system, you can enable it by clicking View -> Cell Toolbar -> Hide Code on your jupyter notebook menu.
![hide code demo](/img/hide_code.gif)

You can install hide_code using following commands:

`pip install hide_code`
`jupyter nbextension install --py hide_code`
`jupyter nbextension enable --py hide_code`
`jupyter serverextension enable --py hide_code`

You can export your notebooks to desired format using the following commands:
To HTML <br>
`jupyter nbconvert --to hide_code_html notebook_to_convert.ipynb`<br>
`jupyter nbconvert --to hide_code_pdf notebook_to_convert.ipynb`<br>
`jupyter nbconvert --to hide_code_latexpdf notebook_to_convert.ipynb`<br>

#### [Tabulate](https://bitbucket.org/astanin/python-tabulate/src/master/)
Tabulate is a python package used for pretty printing tabular data in python.
You can install tabulate using either of the following commands:
`pip install tabulate`
`conda install -c conda-forge tabulate`

### Creating the notebook
I have created a [demo notebook](https://github.com/alephthoughts/JupyterPublishDemo) on github which you can fork or download or work with your own example. 

#### Writing Narrative Text
In order to write the narrative text in Markdown or HTML, click on "Cell -> Cell Type -> Markdown" on jupyter menu or press "Esc + m" on your keyboard. This [tutorial](https://www.markdowntutorial.com/) gives a good introduction on markdown.

#### Enable Hide_Code
Enable Hide_Code which gives you options to "Hide Prompt", "Hide Code" and "Hide Cell" on the top right corner of each cell in the notebook. Using the following command convert your notebook to LaTeX format.
`jupyter nbconvert --to hide_code_latex notebook_to_convert.ipynb`

#### Adding colors to your LaTeX file
By default the export is black and white.You can add color to your latex element by using the following command:<br>
`{\color{<color name>}<element text>}`<br>

You can color entire sections using the following global definitions: <br>
`\usepackage{sectsty}`
`\chapterfont{\color{brown}}`
`\sectionfont{\color{brown}}`
`\subsectionfont{\color{brown}}`
`\subsubsectionfont{\color{teal}}`
`\date{\color{brown}June 10, 2019}`

You can deep dive into [LaTeX](https://www.latex-tutorial.com/tutorials/?ref=hackr.io) if you want to customize it completely. <br>
This brings us to the end of this post. Hope you will find it useful!

