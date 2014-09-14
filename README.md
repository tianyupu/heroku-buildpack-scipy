Heroku buildpack: Python, NumPy, and SciPy
====================================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
for Python apps, powered by [pip](http://www.pip-installer.org/).

This custom buildpack currently supports only NumPy 1.8.1 and SciPy 0.14.0
installations, and extends upon previous buildpacks by supporting both the
latest stable Python runtimes (2.7.8 and 3.4.1) on Heroku.

Please open a GitHub for any problems encountered or feature requests. If you
are interested in seeing a write-up/tutorial for creating this custom
buildpack, please let me know in a GitHub issue.

Details
-------

This buildpack currently only supports these versions of NumPy and SciPy:

- NumPy 1.8.1
- SciPy 0.14.0

This package will also install compiled runtime libraries for BLAS, LAPACK,
ATLAS, and Fortran, which are needed by NumPy and SciPy at runtime.

If you desire older NumPy or SciPy packages, please take a look at
https://github.com/dbrgn/heroku-buildpack-python-sklearn.

Usage
-----
For a new app:

    heroku create --buildpack https://github.com/tianyupu/heroku-buildpack-scipy

For an existing app:

    heroku config:set BUILDPACK_URL=https://github.com/tianyupu/heroku-buildpack-scipy

Demo
----

    $ mkdir testheroku
    $ cd testheroku
    $ git init
    $ heroku create --buildpack https://github.com/tianyupu/heroku-buildpack-scipy
    $ echo -e "numpy==1.8.1\nscipy==0.14.0" > requirements.txt
    $ git add requirements.txt
    $ git commit -m 'Added requirements for scipy 0.14.0 and numpy 1.8.1'
    $ git push heroku master


Acknowledgments
---------------

This fork is taken from @thenovices - thanks to him and others, I've been able
to create this buildpack.
