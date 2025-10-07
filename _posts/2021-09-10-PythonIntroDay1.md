---
layout: post
title: "Python Intro Day 1"
date: 2021-09-10
excerpt: "A blog post for Washington State University's Python Working Group Blog. This post is the first in a two-part series of introductory python talks for the start of the semester."
tags: [python]
comments: false
---

## A blog post for Washington State University's Python Working Group Blog
<br><br>
This post is the first in a two-part series of introductory python talks for the start of the semester.
The majority of this talk is based on [Software Capentry's Python Notice Inflammation lesson](https://swcarpentry.github.io/python-novice-inflammation/).
<br><br>
---

<p>Watch the <a href="https://youtu.be/5YA29G6BCQw">recording of the presentation here</a>. Presentation by <a href="https://sarahymurphy.github.io/">Sarah Murphy</a> (sarah.y.murphy@wsu.edu). Data used in this lesson can be <a href="https://drive.google.com/drive/folders/1GbdShqmVXEefoFj9j7yYmGxDLMPvpveH?usp=sharing">downloaded here</a>. We will use the inflammation-01.csv file in the Data folder for this lesson.&nbsp;</p>

<h3>Some vocabulary</h3>
<ul>
<li><b>Library</b> - Families of code. You can import these to give you extra tools</li>
<li><b>Variable</b> - A value with a name assigned to it.</li>
<li><b>Function</b> - A named group of code. Can be imported by itself or with a library.</li>
<li><b>Arguments/Parameters</b> - Variables or values given to a function.</li>
</ul>
<h3>Getting Python on your computer</h3>
<ul>
<li>Download Python on it's own (<a href="https://www.python.org/downloads/">https://www.python.org/downloads/</a></li>
<li>I use Anaconda: <a href="https://www.anaconda.com/">https://www.anaconda.com/</a>. This comes with <b>Jupyter Notebook</b> and <b>Spyder</b>. It also comes with a library manager (<b>conda</b>).</li>
</ul>

<!-- wp:separator {"customColor":"#9c2f19","align":"center","className":"is-style-wide"} -->
<hr class="wp-block-separator aligncenter has-text-color has-background is-style-wide" style="background-color:#9c2f19;color:#9c2f19"/>
<!-- /wp:separator -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Fri Sep 10 11:58:43 2021

@author: smurphy
"""

weight_kg = 60

# Defining variables
## Includes letters, digits, and underscores
## Case sensitive
## 0weight, 1weight doesnt work, can't start with a number


# floating point number
floatingnumber = 60.2
floatingnumber_2 = 60.0

# integer
integernumber = 60

# strings
stringnumber = '20'

weight_lb = 2.2 * weight_kg

print('The weight in kg is ', weight_kg)

print(type(weight_kg))

print(type(stringnumber))


import numpy

text_file = numpy.loadtxt(fname = '/Users/smurphy/swc-python/data/inflammation-01.csv',
              delimiter = ',')

import matplotlib.pyplot as plt

plt.plot(text_file[:,0])
</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:image {"align":"center","id":109,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/download.png?w=378" alt="" class="wp-image-109"/><figcaption>The figure created by the code above using the inflammation-01.csv dataset.</figcaption></figure></div>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="references">References</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Dataset and rough outline of code comes from the Software Carpentry lesson (<a href="https://swcarpentry.github.io/python-novice-inflammation/">https://swcarpentry.github.io/python-novice-inflammation/</a>)<ul><li>Lesson primarily from the <a href="https://swcarpentry.github.io/python-novice-inflammation/01-intro/index.html">Python Fundamentals</a> lesson, vocabulary from the <a href="https://swcarpentry.github.io/python-novice-inflammation/reference.html">Reference</a> section. </li></ul></li></ul>
<!-- /wp:list -->
