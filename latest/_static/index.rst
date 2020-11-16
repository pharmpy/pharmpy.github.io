=========================
Welcome to Pharmpy |logo|
=========================

.. |logo| image:: Pharmpy_logo.svg
   :width: 100

Pharmpy is a library for pharmacometrics. It can be used as a regular python package, in R via
reticulate or via its built in command line interface. The API of Pharmpy is model agnostic and
the library is architectured to be able to handle different types of model and data formats (currently
only NONMEM is supported).

Current features include:

* Parsing of many parts of a NONMEM model file
* Parsing of NONMEM result files
* Transformations of models (such as setting absorption rates, adding covariate effects etc.)
* Generating NONMEM code for modified models
* CLI supporting dataset filtering, resampling, anonymization and viewing as well as model transformations

Pharmpy is developed by the Uppsala University Pharmacometrics group.

Contents
========


.. toctree::
   :maxdepth: 2

   installation
   getting_started
   user_guide
   Documentation <reference/modules>
   development
   changelog
   license

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

