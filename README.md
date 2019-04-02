# python-ml-setup
Here I note down some common problems one might encounter in setting up python for machine learning. Mainly for my own reference, or if you are a student learning machine learning with python for the first time this might also help you. 

For students currently in NYU Shanghai's ML class (Spring 2019), if you have general questions on python setup, you can post an issue here. Or come to my office hour.

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




