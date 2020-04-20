# python-ml-setup
Here I write down some common steps and common problems one might encounter in setting up python for machine learning. Mainly for my own reference, or if you are a student learning machine learning with python for the first time this might also help you. 

CURRENT 2020 Spring ML students: if you are having difficulty setting up the environment, you can open an issue here.

# IMPORTANT: PREPARE FOR YOUR FIRST PYTORCH CLASS
(If you find difficulty on any step, then simply don't worry about it, we will talk in class. But if you can manage to get these set up by class time, it would help you understand things faster)
Highly recommended:
1. Download and install anaconda if you haven't. This is very easy. 
2. Scan through this page to have a quick understanding of conda virtual environments, at least read how to create and activate environment: https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html
3. In mac/ubuntu, open a terminal and run `conda create -n ml python=3.6` to create a conda virutal environment. In windows, open anaconda power shell instead of windows terminal. (search "anaconda" in your windows search bar, after you installed anaconda) If you already have a environment with python 3.6+ and pytorch 1.0+ then you can also skip these 2 steps, and just use your old environment. 
4. go to pytorch website and install pytorch in your "ml" environment (don't forget to activate it). Then, in your "ml" environment, run python and see if you can `import torch`. If you don't have pytorch installed previously, simply install latest version. 
5. activate ml environment, run python, try `import torch`.

Optional, but still recommended:
1. use a more advanced IDE. My recommendation is pycharm. Install pycharm and learn about how to create a project, and how to set the correct interpreter, create a project and set it to use your virtual env's interpreter: https://www.jetbrains.com/help/pycharm/configuring-python-interpreter.html
2. install git on your machine. 
3. in your ml environment, install the following packages if you haven't: numpy, pandas, matplotlib, sklearn, scipy
4. learn the super powerful pycharm debugger, make your debugging experience happier: https://www.youtube.com/watch?v=QJtWxm12Eo0

# resources for beginners
Students come out of an ICP class, mastering the basic syntax of python, but when they start deal with more complex projects, they suffer hugely from things that are outside their code. For example, you might not have a good understanding of python path and your code simply don't run when they import stuff, or you don't know what is a virtualenv and get package conflict, or you don't know what github is and your team simply don't collaborate, or you don't know how to use a terminal, and you get lost when you connect to the hpc. It can be EXTREMELY helpful to watch a few tutorials and get a basic knowledge of these things... here are some recommendations. 

Python path, module, package:
https://www.youtube.com/watch?v=UK97NoQK23k&t=469s

# common python basics problems

## my python packages are chaotic and in conflict.
A good solution is use virtualenv, or use anaconda + anaconda's virtual env. I found this to be very effective. What is virtual env? Look at the tutorial here: https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/

## I use a conda env, I think I have correct version of package, but I installed stuff with conda but also with conda's pip and my python is running wrong version of the package.
It's generally OK to enter a conda env, and then use pip install to install stuff. I believe the pip here is conda's pip. And the packages are correctly installed to your conda env. But sometimes you can have multiple versions of same packages in one conda env. 
Check the packages installed in your conda env by `conda list -n <your-env-name>`, you might find that you have a package, for example numpy, with 2 different versions, one installed by pip, one by conda (it can happen sometimes, and will cause messy version conflict), you might want to simply uninstall one of them, and then make sure the only one existing is of the correct version. 

## jupyter notebook doesn't show anaconda kernels
What worked for me is this tutorial on https://github.com/jupyter/jupyter/issues/245#issuecomment-287080203
Basically, first enter your conda env, then `conda install ipykernel`, then `conda install --channel=conda-forge nb_conda_kernels`.

## why is jupyter notebook behaving differently from python file, why do I get different result running a cell twice?
Once you run a cell, jupyter notebook save variables in your memory, that means a bunch of variables are in your memory and sometimes you might want to reset the whole notebook. If some calculation in a cell depends on variables defined in other cells, particularly defined in previously run cells, when you run a cell for a second time very likely get a different result. 

# common pytorch, numpy problems

## I simply cannot load a file?
Check your path. Is your program and your data in the same directory? Are you using relative path? Or absolute path? Print out your current path in your program, print out the path that you want to load your data, see if this information is the same as what you imagined. 

## pytorch says I might have incorrect broadcast? What does that mean?
Check the shape of your tensors, print them out or use debugger. For example, if you use a tensor of shape (4,1) added to a tensor of shape (4,1), you will get tensor of shape (4,1). But if you added a tensor of shape (4) to a tensor of shape (4,1), you get (4,4), which might or might not be what you want. 
Always try to broadcast explicitly (for example, expand their shape) to avoid such problems. 

