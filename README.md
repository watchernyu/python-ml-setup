# python-ml-setup
Here I note down some common problems one might encounter in setting up python for machine learning. Mainly for my own reference, or if you are a student learning machine learning with python for the first time this might also help you. 

## jupyter notebook doesn't show anaconda kernels
In short, do `conda install nb_conda` in your anaconda env, or watch the 5 min tutorial here: 
https://www.youtube.com/watch?v=Ro9l0eapoJU

## why is jupyter notebook behaving differently from python file, why do I get different result running twice a cell
Once you run a cell, jupyter notebook save variables in your memory, that means a bunch of variables are in your memory and sometimes you might want to reset the whole notebook. If some calculation in a cell depends on variables defined in other cells, particularly defined in previously run cells, when you run a cell for a second time very likely get a different result. 




