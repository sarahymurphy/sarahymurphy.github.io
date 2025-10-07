---
layout: post
title: "Python Intro Day 2"
date: 2021-09-17
excerpt: "A blog post for Washington State University's Python Working Group Blog. This post is the second in a two-part series of introductory python talks for the start of the semester."
tags: [python]
comments: false
---

## A blog post for Washington State University's Python Working Group Blog
<br><br>
This post is the second in a two-part series of introductory python talks for the start of the semester.
The majority of this talk is based on [Software Capentry's Python Notice Inflammation lesson](https://swcarpentry.github.io/python-novice-inflammation/).
<br><br>
---

<!-- wp:paragraph -->
<p>This week <a href="https://sarahymurphy.github.io/">Sarah Murphy</a> (sarah.y.murphy@wsu.edu) gave the second in a two-part series of introductory talks. <a href="https://youtu.be/kh0Pe9UqPkY">A recording of this talk can be found here</a>. Instructions on how to <a href="https://drive.google.com/drive/folders/1GbdShqmVXEefoFj9j7yYmGxDLMPvpveH?usp=sharing">download the required packages and the data used in this lesson can be found here</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="introduction-to-jupyter-notebooks">Introduction to Jupyter Notebooks</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://jupyter.org/">Jupyter Notebook and Jupyter Lab</a> are two Python coding interfaces. They both take the "notebook" approach, meaning they can combine markdown, or text, with code. They have similar interfaces and can be used in the same way, so I will be referring to the two collectively as Jupyter for the rest of this talk. These come as part of the Anaconda set of tools, meaning if you have Anaconda downloaded, you also have Jupyter. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>When you open Jupyter Lab or Notebook from your Anaconda navigator, a file browser interface will open within a web browser.  Your default web browser serves as a way to display Jupyter, you do not need an internet connection to use it and nothing is uploaded. To create a new notebook, navigate to where you would like it to reside in your file system, then click "New" or "+". This will bring up a menu asking what type of file you would like to create. Select "Python 3" under the "Notebook" heading. Your new notebook is a .ipynb file, or an iPython Notebook file. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>When you open your notebook, you will see an empty space to type. This is referred to as a <strong>cell</strong>. Cells can be either <strong>code cells</strong> or <strong>markdown cells</strong>. Code cells are for just that, code. Markdown cells allow you to write text with the ability to format it using markdown. If you don't know markdown, that's okay, you don't need to. You can switch between the two types of cells using the dropdown menu at the top of the notebook.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In our first code cell, we can code in Python just as we did with Spyder on day 1. </p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">a = 15
print(50)</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>To run your code cell, or to format text in markdown cells, you can either hit the "run" button at the top of the notebook or hold shift and press enter. Either option will run your current cell, display any output below the cell, and create a new one.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="revisiting-types">Revisiting Types</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>During last week's talk, there were some questions about types, so this week we took some time to dig into this a bit more.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">a = 50
type(a) # Shows that a is an integer</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>When we check the type of a variable which contains a number without a decimal it returns 'int', indicating that it is an integer. However, if we wanted to change this integer to a floating point number or string, we can do that with the following commands:</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">float(a) # Gives a as a floating point number (50.0)
str(a) # Gives a as a string ('50')</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p> It is important to be aware of types when doing math. A number stored as a string cannot be used in calculations.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">a = 50 # Defining a as an integer
b = 27 # Defining b as an integer
b = str(b) # Converting b to a string

a + b # This will give you an error because the variable b is a string</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:heading {"level":3} -->
<h3 id="introduction-to-loops">Introduction to Loops</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>First, let's define a list of odd numbers:</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">odds = [1, 3, 5]
print(odds)</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>We can print out the entire list at once by printing it out as we have above. If we wanted to only select one of those values, we can indicate the location of the value using square brackets. <strong>Note that Python starts counting at zero, not one,</strong> so the first place in the list is considered index number zero in Python.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">print(odds[0]) # This will give you 1
print(odds[1]) # This will give you 3
print(odds[2]) # This will give you 5</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>If we want to print all the values out one by one, we could do it as we have above. But what if we change the variable 'odds'? What would happen if we tried to print the three values but our list is only two values long?</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">odds = [1, 3]

print(odds[0]) # This will still give you 1
print(odds[1]) # This will still give you 3
print(odds[2]) # This will now give you an error</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>This means that if we make any changes to the length of the original list, we will either get an error or we won't see all of the values in the list. To avoid this, we can utilize loops!</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A loop can be defined using the following formula:</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python","align":"center"} -->
<pre class="wp-block-syntaxhighlighter-code aligncenter">for variable in collection:</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p><strong>Where collection is your list, and variable is a placeholder variable you can select</strong>. It doesn't matter what you select for variable, as long as it isn't the name of another variable within your code. After this line of code, hit return, Python will automatically indent your next line. Everything within the loop should have this indentation for Python to understand it should be grouped together. To end the loop, just continue to write your code without the indentation.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">odds = [1, 3, 5]

for num in odds:
     print(num) # This will print each value on it's own line</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>In our situation, our collection is 'odds', the list we defined above, and 'num' is the placeholder variable. What does does is sets 'num' equal to the first value in the 'odds' list, executes the indented code (in this case print(num)), then returns to the top of the loop, sets 'num' to the next value in 'odds', and, again, executes the indented code. All variables defined outside the loop can be used within it, and all variables defined within the loop can be used outside of it.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We can do math within a loop, too: </p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">names = ['Python', 'R', 'MATLAB'] # Create a list of strings
length = 0 # Create a variable for us to do math with, we will start our addition at zero

# Below is the loop:
for value in names: # Set "value" equal to each string in "names"
    print('The current name is:', value) # Print what the variable "value" currently is set to
    length = length + 1 # Add 1 to the length
    print('The new length is', length) # Print the current length</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>The above code should give you the following output: </p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code -->
<pre class="wp-block-syntaxhighlighter-code">The current name is: Python
The new length is 1
The current name is: R
The new length is 2
The current name is: MATLAB
The new length is 3</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>Each time we looped through the code, length increased by one each time the line 'length = length + 1' was run, showing that we can build upon a variable within a loop.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="plotting-refresher">Plotting Refresher</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Before we can start importing data and plotting it, we need to import the libraries <strong>numpy</strong> and <strong>pyplot from</strong> <strong>matplotlib</strong> by using the following import commands. Note that we are setting both equal to an <strong>alias</strong> (shortened nicknames to use in your code, in this case np and plt, respectively).</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">import numpy as np
import matplotlib.pyplot as plt</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>We imported numpy so we can import the data. We will use the 'np.loadtxt' command with two arguments, 'fname' and 'delimiter'. The argument 'fname' is the path to your data and 'delimiter' refers to the character being used to separate values within your csv or text file. In this case, our delimiter is a comma.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">data = np.loadtxt(fname='inflammation-01.csv', delimiter = ',')</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>Now, we can plot the mean of the data just as we did last week.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">plt.figure(figsize = (5, 5)) # Create one figure with the size 5 x 5
plt.plot(np.mean(data, axis = 0)) # Plot the mean of data, taken across the 0th axis (rows)
plt.title('Average Data') # Give the plot a title</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:image {"align":"center","id":135,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/download-1.png?w=313" alt="" class="wp-image-135"/></figure></div>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="using-glob">Using Glob</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We can import the library 'glob' to read in multiple files at once. The glob.glob command searches for all files matching the criteria specified in parenthesis. For example, below we are printing all files that have the extension .csv in the directory my notebook is in.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">import glob
print(glob.glob('*.csv')</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>Glob doesn't guarantee any specific order, so you can sort the list using the sorted command.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">filenames = sorted(glob.glob('*.csv')) # Save a sorted list of all the .csv files in this directory to the variable 'filename'</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:heading {"level":3} -->
<h3 id="creating-images-from-multiple-files-with-loops">Creating images from multiple files with loops</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We can combine everything we've learned today by looping through a list of files and creating a figure of each. </p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code {"language":"python"} -->
<pre class="wp-block-syntaxhighlighter-code">filenames = sorted(glob.glob('*csv'))

for filename in filenames: # Set the strings in the variable 'filenames' equal to 'filename' one by one
    print(filename) # Print the current filename
    data = np.loadtxt(fname = filename, delimiter = ',') # Load the current file
    plt.figure(figsize = (5, 5))
    plt.plot(np.mean(data, axis = 0))
    plt.title('Average Data')
    plt.show() # Show the plot</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:image {"align":"center","id":139,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/screen-shot-2021-09-27-at-3.02.38-pm.png?w=256" alt="" class="wp-image-139"/></figure></div>
<!-- /wp:image -->

<!-- wp:image {"align":"center","id":141,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/screen-shot-2021-09-27-at-3.02.47-pm.png?w=256" alt="" class="wp-image-141"/></figure></div>
<!-- /wp:image -->

<!-- wp:image {"align":"center","id":142,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/screen-shot-2021-09-27-at-3.02.53-pm.png?w=255" alt="" class="wp-image-142"/></figure></div>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="references">References</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li><a href="https://jupyter.org/">Project Jupyter</a></li><li><a href="https://www.anaconda.com/">Anaconda</a></li><li><a href="https://swcarpentry.github.io/python-novice-inflammation/04-lists/index.html">Programming with Python - Storing Multiple Values in Lists Software Carpentry lesson</a> </li><li><a href="https://swcarpentry.github.io/python-novice-inflammation/05-loop/index.html">Programming with Python - Repeating Actions with Loops Software Carpentry lesson</a></li><li><a href="https://swcarpentry.github.io/python-novice-inflammation/06-files/index.html">Programming with Python - Analyzing Data from Multiple Files</a></li></ul>
<!-- /wp:list -->
