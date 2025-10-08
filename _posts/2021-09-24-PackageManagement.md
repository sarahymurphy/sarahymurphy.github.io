---
layout: post
title: "Package Management in Python"
date: 2021-09-24
excerpt: "A blog post for Washington State University's Python Working Group Blog about how to install and manage packages in Python."
tags: [python]
comments: false
---

The majority of this talk is based on talk was based on the <a href="https://docs.conda.io/projects/conda/en/latest/user-guide/index.html">conda user guide</a> and the <a href="https://packaging.python.org/tutorials/installing-packages/">Python Packaging Authority website.</a>
<br><br>

<hr>

<!-- wp:paragraph -->
<p>This week <a href="https://sarahymurphy.github.io/">Sarah Murphy</a> (sarah.y.murphy@wsu.edu) gave a talk about managing packages and environments using conda and pip. <a href="https://youtu.be/614MJmzlVGY">A recording of the talk can be seen here.</a> </p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="vocabulary">Vocabulary </h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li><strong>Library/Package</strong> - A collection of code (or modules) that you can import and use in your code. <ul><li>These can contain functions and constants.</li></ul></li><li><strong>Module</strong> - The files that make up a library.<ul><li>Note: People often use module and library interchangeably even though they are not the same thing.</li><li>Many libraries are only one module.</li></ul></li><li><strong>Environment</strong> - An isolated Python distribution with its own installation and packages.</li><li><strong>Package manager</strong> - Software for downloading and upgrading Python libraries.</li><li><strong>Anaconda</strong> - A set of tools for coding (<a href="https://www.anaconda.com/">https://www.anaconda.com/</a>).</li><li><strong>conda</strong> - A package manager that comes with Anaconda.</li><li><strong>pip</strong> - The Python package manager.</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="pip-vs-conda">Pip vs Conda</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The two most popular package managers for Python are pip and conda. Both have advantages and disadvantages, and it is likely you will need to use both. Pip typically comes with your Python download, so there is no need to download any additional software. Conda comes as part of Anaconda.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li><a href="https://pypi.org/project/pip/">Pip</a></li><li><a href="https://docs.conda.io/en/latest/">Conda</a></li></ul>
<!-- /wp:list -->

<!-- wp:table {"align":"center","className":"is-style-stripes"} -->
<figure class="wp-block-table aligncenter is-style-stripes"><table><tbody><tr><td></td><td class="has-text-align-left" data-align="left"><strong>Pip</strong></td><td class="has-text-align-left" data-align="left"><strong>Conda</strong></td></tr><tr><td>Who created it?</td><td class="has-text-align-left" data-align="left">Python Package Authority</td><td class="has-text-align-left" data-align="left">Anaconda</td></tr><tr><td>Where are packages downloaded from?</td><td class="has-text-align-left" data-align="left">Python Package Index</td><td class="has-text-align-left" data-align="left">Anaconda repository and cloud</td></tr><tr><td>Can it include software written in other languages?</td><td class="has-text-align-left" data-align="left">Not without downloading other things</td><td class="has-text-align-left" data-align="left">Yes</td></tr><tr><td>Can it create environments?</td><td class="has-text-align-left" data-align="left">Yes, with venv</td><td class="has-text-align-left" data-align="left">Yes</td></tr></tbody></table><figcaption>Some of the key differences between pip and conda as package management software</figcaption></figure>
<!-- /wp:table -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><p>A major reason for combining pip with conda is when one or more packages are only available to install via pip</p><cite>The Anaconda Blog</cite></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Conda commands can be executed in the command line software of your choosing. As a Mac user, I always use Terminal for this. Alternatively, you can open a Spyder document and execute the commands from the console.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Pip commands can also be executed in the command line software of your choosing. <strong>You will notice the pip commands below say 'python3' followed by the rest of the command. On a Windows computer, you would replace 'python3' with 'py'.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="packages">Packages</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>For the sake of this demonstration, I will be using the commands as if they were typed into the Terminal on a Mac. Additionally, all commands below will use 'scipy' as the package of choice. Replace scipy with your package.</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="installing-packages">Installing Packages</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>sIt's easy to install package with both conda and pip. It's useful to know how to use both because some packages are only available via pip or an alternative channel through conda. A <strong>channel</strong> is a location that conda can look for code to download. Most of the time, you won't specify a channel with conda, meaning conda will search the default library for your code. </p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p> The command to install a package with conda is install: </p>
<!-- /wp:paragraph -->

```bash
conda install scipy
```

<!-- wp:paragraph -->
<p>You can also list multiple packages after the install command to download them all. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If you'd like to install a specific version of a package, set the package name equal to the version you'd like.</p>
<!-- /wp:paragraph -->

```bash
conda install scipy = 0.15.0
```

<!-- wp:paragraph -->
<p>There is the possibility that you may need to download a package from conda that is not provided by the default channel. One of the most popular alternative channels is <strong>conda-forge</strong>. To specify that we want to search a different channel, we will use the -c flag with the above commands and followed by the channel.</p>
<!-- /wp:paragraph -->

```bash
conda install -c conda-forge scipy
```

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>With pip, we use the command 'python3 -m pip install' to install packages. Note that this would be 'py -m pip install' on a Windows computer.</p>
<!-- /wp:paragraph -->

```bash
python3 -m pip install "scipy"
```

<!-- wp:paragraph -->
<p>Just as with conda, there is the option to specify the package version.</p>
<!-- /wp:paragraph -->

```bash
python3 -m pip install "scipy = 0.15.0"
```

<!-- wp:heading {"level":3} -->
<h3 id="searching-for-packages">Searching for Packages</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The search command can be used in both pip and conda to find information about packages that are both installed and not installed.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

```bash
conda search scipy
```

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

```bash
pip search scipy
```

<!-- wp:heading {"level":3} -->
<h3 id="what-packages-do-i-already-have-installed">What packages do I already have installed?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>You can see packages you have downloaded using the list command in conda and pip and the freeze command in pip. Both of these commands can be output to a file by using the greater than symbol (&gt;) after the command followed by the output file name (conda list &gt; packages.txt).</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

```bash
conda list
```

<!-- wp:paragraph -->
<p>Conda's list command displays a table containing the package name, version, build, and channel. The channel is only displayed if it was downloaded from a channel other than the default.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

```bash
pip list
pip freeze
```

<!-- wp:paragraph -->
<p>Pip's list command displays a neat table of your package names and versions. Using freeze will display more information, including some file paths, but is not formatted in the same way.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="removing-packages">Removing Packages</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Removing a package is just as easy as installing it. You can use the remove command in conda and uninstall in pip.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

```bash
conda remove scipy
```

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

<!-- wp:syntaxhighlighter/code -->
<pre class="wp-block-syntaxhighlighter-code">pip uninstall scipy
```

<!-- wp:heading {"level":3} -->
<h3 id="updating-packages">Updating Packages</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>You can update packages using the update command in conda and the install command with the upgrade flag in pip. </p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

```bash
conda update scipy
```

<!-- wp:paragraph -->
<p>The update command is the same for updating conda, anaconda, spyder, and all other anaconda products, too! </p>
<!-- /wp:paragraph -->

```bash
conda update conda
conda update anaconda
conda update spyder
```

<!-- wp:paragraph -->
<p>In conda, we can pin packages. <strong>Pinning</strong> is when you tell conda not to update a package. I will go into more detail about how to pin packages in the next section. If you want to update a package that you've pinned, you can use the update command with the --no-pin flag.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code -->
<pre class="wp-block-syntaxhighlighter-code">conda update scipy --no-pin
```

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

```bash
pip install --upgrade scipy
```

<!-- wp:heading {"level":3} -->
<h3 id="pinning-packages">Pinning Packages</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Pinning</strong> is telling conda not to update a package. To do this, you must create a text document in the 'conda-meta' directory. Mine is located here:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center">/Users/smurphy/opt/anaconda3/conda-meta</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>This file must be named 'pinned'.</strong> List the packages and versions in this document, with each on its own line.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":171,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/screen-shot-2021-09-27-at-4.59.36-pm.png?w=284" alt="" class="wp-image-171"/><figcaption>An example of the 'pinned' text file in the 'conda-meta' directory</figcaption></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>You can either set a package to stay at a specific version (scipy in the above image, will stay at version 1.14.2), or not update out of a series (numpy in the above image, will update throughout all of 1.7, but will not update to 1.8).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If you have multiple environments, which I'll discuss in the following sections, you can have a pinned file for each environment in the environment's conda-meta directory.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="environments">Environments</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Environments allow users to have separate installations of python with isolated installations of libraries. Starting a new environment will essentially start you a clean version of python with nothing downloaded without disrupting other versions.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The examples below show how to create a new environment named "myenv." <strong>Change "myenv" to whatever you'd like your environment to be called.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="creating-an-environment">Creating an Environment</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We can use the create command in conda to create a new environment.</p>
<!-- /wp:paragraph -->

```bash
conda create -n myenv
```

<!-- wp:paragraph -->
<p>If we would like a past version of Python we can specify it the same way we specify package versions.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code -->
<pre class="wp-block-syntaxhighlighter-code">conda create -n myenv python=3.6
```

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Pip uses venv to create virtual environments and does not have the ability to specify Python version within the create command. </p>
<!-- /wp:paragraph -->

```bash
py -m venv myenv
```

<!-- wp:heading {"level":3} -->
<h3 id="activating-and-deactivating-environments">Activating and Deactivating Environments</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To use an environment, you must <strong>activate</strong> it through the command line. If you do not activate an environment, you are using the default environment, and all installations will only apply to the default environment. <strong>Deactivate</strong> an environment to return to your default environment. Activating and deactivating can be thought of like logging into and out of environments you've created.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="conda">Conda</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To activate your environment in conda, use the activate command. </p>
<!-- /wp:paragraph -->

```bash
conda activate myenv
```

<!-- wp:paragraph -->
<p>With older verisions of Python and conda, you may need to use source in the place of conda.</p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code -->
<pre class="wp-block-syntaxhighlighter-code">source activate myenv
```

<!-- wp:paragraph -->
<p>It is likely both of these commands will work for you.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>To deactivate environments in conda, we use the deactivate command.</p>
<!-- /wp:paragraph -->

```bash
conda deactivate
```

<!-- wp:heading {"level":4} -->
<h4 id="pip">Pip</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Activating environments with pip is different for Mac and Windows users. For <strong>Mac users</strong> we use the source command followed by the environment name and '/bin/activate'. </p>
<!-- /wp:paragraph -->

```bash
source myenv/bin/activate
```

<!-- wp:paragraph -->
<p>For <strong>Windows users</strong> we use the following command, replacing myenv with the name of your environment.</p>
<!-- /wp:paragraph -->

```bash
.\myenv\Scripts\activate
```

<!-- wp:paragraph -->
<p>To deactivate, we can just type deactivate.</p>
<!-- /wp:paragraph -->

```bash
deactivate
```

<!-- wp:heading {"level":3} -->
<h3 id="sharing-environments">Sharing Environments</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>If you use multiple computers or often share code with a colleague, it may be helpful for you to create a standardized environment. You can do this by creating an environment.yml file for conda to use when creating a new environment. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The environment.yml file is text file. This file can be created anywhere in your system, but you must be sure to either create the new environment from the directory with this file or use the file path in the command. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":184,"sizeSlug":"large","linkDestination":"none"} -->
<div class="wp-block-image"><figure class="aligncenter size-large"><img src="https://cougpy.files.wordpress.com/2021/09/screen-shot-2021-09-27-at-5.17.17-pm.png?w=444" alt="" class="wp-image-184"/><figcaption>An example environment.yml file</figcaption></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The example file above would create an environment named 'stats2'. The dependencies listed are the packages to install. Some packages have specified versions to download. Those without will download the most recent release. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Once you have an environment.yml file, you can use the following code to create the environment:</p>
<!-- /wp:paragraph -->

```bash
conda env create -f environment.yml
```

<!-- wp:paragraph -->
<p>Now, you can use the environment 'stats2' by activating it just as we did before. If you'd like to share this environment, just send your environment.yml file. Your collaborators will be able to create a new environment with it just like you did.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="summary-of-commands">Summary of Commands</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="packages">Packages</h3>
<!-- /wp:heading -->

<!-- wp:table {"align":"center","className":"is-style-stripes"} -->
<figure class="wp-block-table aligncenter is-style-stripes"><table><tbody><tr><td></td><td><strong>Pip</strong></td><td><strong>Conda</strong></td></tr><tr><td>Installing</td><td>pip install scipy</td><td>conda install scipy</td></tr><tr><td>Updating</td><td>pip install --upgrade scipy</td><td>conda update scipy</td></tr><tr><td>Removing</td><td>pip uninstall scipy</td><td>conda remove scipy</td></tr></tbody></table><figcaption>A summary of the most common package commands using pip and conda</figcaption></figure>
<!-- /wp:table -->

<!-- wp:heading {"level":3} -->
<h3 id="environments">Environments</h3>
<!-- /wp:heading -->

<!-- wp:table {"align":"center","className":"is-style-stripes"} -->
<figure class="wp-block-table aligncenter is-style-stripes"><table><tbody><tr><td></td><td><strong>Pip</strong></td><td><strong>Conda</strong></td></tr><tr><td>Creating</td><td>python3 -m venv myenv</td><td>conda create -n myenv</td></tr><tr><td>Activating</td><td>Run the activate file</td><td>conda activate myenv</td></tr><tr><td>Deactivating</td><td>deactivate</td><td>conda deactivate</td></tr></tbody></table><figcaption>A summary of the most common environment commands using pip and conda</figcaption></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="additional-resources">Additional Resources</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li><a href="https://docs.conda.io/projects/conda/en/latest/commands.html#conda-vs-pip-vs-virtualenv-commands">A better side-by-side of pip vs conda commands.</a></li><li><a href="https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf">Anaconda's Conda Cheat Sheet</a></li><li><a href="https://opensource.com/sites/default/files/gated-content/cheat_sheet_pip.pdf">Opensource.com's pip Cheat Sheet</a></li><li><a href="https://conda-forge.org/">Conda-forge</a></li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>If you'd like information about package management using the Anaconda Navigator, I touch on this briefly near the end of the <a href="https://youtu.be/614MJmzlVGY">YouTube video</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="references">References</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
- <a href="https://docs.conda.io/projects/conda/en/latest/user-guide/index.html">Conda user guide</a>
- <a href="https://packaging.python.org/tutorials/installing-packages/">Python Packaging Authority website.</a>
<!-- /wp:paragraph -->
