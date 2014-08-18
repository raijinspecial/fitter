

#############################
FITTER documentation
#############################

.. image:: https://badge.fury.io/py/fitter.svg
    :target: https://pypi.python.org/pypi/fitter

.. image:: https://pypip.in/d/fitter/badge.png
    :target: https://crate.io/packages/fitter/

.. image:: https://secure.travis-ci.org/cokelaer/fitter.png
    :target: http://travis-ci.org/cokelaer/fitter

.. .. image:: https://coveralls.io/repos/cokelaer/fitter/badge.png?branch=master 
     :target: https://coveralls.io/r/cokelaer/fitter?branch=master 

.. image:: https://landscape.io/github/cokelaer/fitter/master/landscape.png
   :target: https://landscape.io/github/cokelaer/fitter/master

.. image:: https://badge.waffle.io/cokelaer/fitter.png?label=ready&title=Ready 
   :target: https://waffle.io/cokelaer/fitter






**fitter** package provides a simple class to figure out from whih distribution your data comes from. It uses scipy package to try 80 ditribution and allows you to plot the results to check what is the most probable distribution.


Installation
###################

::

    pip install fitter


Usage
##################


Nothing complicated since there is just one class provided. First, we will need to create some data samples. Let us create
a sequence of 100000 samples from a gamma distribution::

    from scipy import stats
    stats.gamma.rvs(2, loc=1.5, scale=2, size=100000)


Now, the question without any knowledge about the distribution of its parameter, what is a probable distribution that fit the data? scipy has 80 distribution with a method called **fit** that will help us here. The :class:`fitter.Fitter` will scan all the distribution, call the fit function for you, ignoring those that fail or run forever and finally give you a summary of the best distribution in the sense of sum of the square errors. The best is to give an example::


    from fitter import Fitter
    f = Fitter(data)
    f.fit()
    # make take some time since by default, all distribution are tried
    f.summary()


.. image:: http://pythonhosted.org/fitter/_images/index-1_00.png
    :target: http://pythonhosted.org/fitter/_images/index-1_00.png



See the `online <http://pythonhosted.org/fitter/>`_ documentation for details.




