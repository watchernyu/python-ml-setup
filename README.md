# python-ml-setup
Here I note down some common problems one might encounter in setting up python for machine learning. Mainly for my own reference, or if you are a student learning machine learning with python for the first time this might also help you. 

## my python packages are chaotic and in conflict.
A good solution is use virtualenv, or use anaconda + anaconda's virtual env. I found this to be very effective. What is virtual env? Look at the tutorial here: https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/

## I think I have correct version of package, but I installed stuff with conda but also with pip and my python is running wrong version of the package.
Check the packages installed in your conda env by `conda list -n <your-env-name>`, you might find that you have a package, for example numpy, with 2 different versions, one installed by pip, one by conda (it can happen sometimes, and will cause messy version conflict), you might want to simply uninstall one of them, and then make sure the only one existing is of the correct version. 

## jupyter notebook doesn't show anaconda kernels
These two are not integrated well when you install them so you have to install some stuff. In short, do `conda install nb_conda` in your anaconda env, or watch the 5 min tutorial here: 
https://www.youtube.com/watch?v=Ro9l0eapoJU

## why is jupyter notebook behaving differently from python file, why do I get different result running twice a cell
Once you run a cell, jupyter notebook save variables in your memory, that means a bunch of variables are in your memory and sometimes you might want to reset the whole notebook. If some calculation in a cell depends on variables defined in other cells, particularly defined in previously run cells, when you run a cell for a second time very likely get a different result. 




