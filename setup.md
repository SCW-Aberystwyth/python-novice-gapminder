---
layout: page
title: "Setup"
permalink: /setup/
---

## Installing Python Using Anaconda

[Python][python] is a popular language for scientific computing, and great for
general-purpose programming as well. Installing all of its scientific packages
individually can be a bit difficult, however, so we recommend the all-in-one
installer [Anaconda][anaconda].

Regardless of how you choose to install it, please make sure you install Python
version 3.x (e.g., 3.4 is fine). Also, please set up your python environment at 
least a day in advance of the workshop.  If you encounter problems with the 
installation procedure, ask your workshop organizers via e-mail for assistance so
you are ready to go as soon as the workshop begins.

### Windows 

1. Open [http://anaconda.org/distribution/#windows][continuum-windows]
   with your web browser.

2. Download the Python 3 installer for Windows.

3. Double-click the executable and install Python 3 using _MOST_ of the
   default settings. The only exception is to check the 
   **Make Anaconda the default Python** option.

### Mac OS X

1. Open [http://anaconda.org/distribition/#macos][continuum-mac]
   with your web browser.

2. Download the Python 3 installer for OS X.

3. Install Python 3 using all of the defaults for installation.

### Linux

Note that the following installation steps require you to work from the shell. 
If you run into any difficulties, please request help before the workshop begins.

1.  Open [http://anaconda.org/distribution/#linux][continuum-linux] with your web browser.

2.  Download the Python 3 installer for Linux.

3.  Install Python 3 using all of the defaults for installation.

    a.  Open a terminal window.

    b.  Navigate to the folder where you downloaded the installer

    c.  Type

    ~~~
    $ bash Anaconda3-
    ~~~
    {: .bash}

    and press tab.  The name of the file you just downloaded should appear.

    d.  Press enter.

    e.  Follow the text-only prompts.  When the license agreement appears (a colon
        will be present at the bottom of the screen) hold the down arrow until the 
        bottom of the text. Type `yes` and press enter to approve the license. Press 
        enter again to approve the default location for the files. Type `yes` and 
        press enter to prepend Anaconda to your `PATH` (this makes the Anaconda 
        distribution the default Python).

## Getting the Data

The data we will be using is taken from the [gapminder][gapminder] dataset.
To obtain it, download and unzip the file 
[python-novice-gapminder-data.zip]({{page.root}}/files/python-novice-gapminder-data.zip).
In order to follow the presented material, you should launch Spyder (see [Starting Python](#Starting-Python)).

## Starting Python

We will teach Python using the Spyder Intergrate Development Environment (IDE). Spyder is included with Anaconda and can be launched from the graphical Anaconda Navigator or from an Anaconda terminal by typing the command `spyder`. 

~~~
$ spyder
~~~
{: .bash}

[anaconda]: https://www.anaconda.com/distribution/#download-section
[continuum-mac]: https://www.anaconda.com/distribution/#macos
[continuum-linux]: https://www.anaconda.com/distribution/#linux
[continuum-windows]: https://www.anaconda.com/distribution/#windows
[gapminder]: http://gapminder.org
[python]: https://python.org
[video-mac]: https://www.youtube.com/watch?v=TcSAln46u9U
[video-windows]: https://www.youtube.com/watch?v=xxQ0mzZ8UvA
