[Home](../sequence.md) - Github 

# Using Github

All the material for the labs and demos in this class are hosted on
[github](https://github.com/).  Github is a powerful platform
generally used for teams of developers to share files when
collaborating on large projects.  A complete guide to github is available
on the [github guide site](https://guides.github.com/).  

To simply download, run and submit the labs, you only need to understand
a few basic ideas: 
All the files are contained in a *repository*,
[https://github.com/sdrangan/introml](https://github.com/sdrangan/introml).
To access these files, perform the following steps:

*  First, install a git client.  A git client is a software program
will allow you to access the repository.  There are several excellent
clients with GUIs, but a basic command line one is sufficient.
Windows, MacOS and Linux clients can be found in the
[git download page](https://git-scm.com/download).
If you are using a VM on GCP, then `git` is already installed and
you can skip this step.
* Next, download the *entire* repository.  In git, you cannot
easily download a single file.  So, you need to clone the entire repository.
Open a command shell or comand window (in Windows, you can use the
[Windows powershell](https://docs.microsoft.com/en-us/powershell)).
In the command shell type:
~~~bash
    > cd [directory where you want the files on your machine]
    > git clone https://github.com/sdrangan/introml.git
~~~
This will create a directory `introml` with all the files.  You are
now ready to go!
* The repository will change over the course of the class and I will update
material.  To update your local version at any time, open the command
window and type:
~~~bash
    > cd introml
    > git pull
~~~

Github is also a great tool for your own projects, even if you
are working individually.  Using `github` will allow you to keep track of 
the files, develop in an organized manner, and release your work to
a broader audience.
