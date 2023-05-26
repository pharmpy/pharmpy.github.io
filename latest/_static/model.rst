.. _model:

=================
The Pharmpy model
=================

At the heart of Pharmpy lies its non-linear mixed effects model abstraction. A model needs to follow the interface of the base model class :py:class:`pharmpy.model.Model`. This means that any model format can in theory be supported by Pharmpy via subclasses that implement the same base interface. This makes any operation performed on a model be the same regardless of the underlying implementation of the model and it is one of the core design principles of Pharmpy.

~~~~~~~~~~~~~~~~~~
Reading in a model
~~~~~~~~~~~~~~~~~~

Reading a model from a model specification file into a Pharmy model object can be done by using the :py:func:`read_model<pharmpy.modeling.read_model>` function.

.. pharmpy-execute::
   :hide-output:
   :hide-code:

   from pathlib import Path
   path = Path('tests/testdata/nonmem/')

.. pharmpy-execute::
   :hide-output:

   from pharmpy.modeling import read_model

   model = read_model(path / "pheno_real.mod")


Internally this will trigger a model type detection to select which model implementation to use, i.e. if it is an NM-TRAN control stream the Pharmpy NONMEM model class will be selected transparent to the user.

~~~~~~~~~~
Model name
~~~~~~~~~~

A model has a name property that can be read or changed. After reading a model from a file the name is set to the filename without extension.

.. pharmpy-execute::

   model.name

.. _model_write:

~~~~~~~~~~~~~~~
Writing a model
~~~~~~~~~~~~~~~

A model object can be written to a file using its source format. By default the model file will be created in the current working directory using the name of the model.

.. pharmpy-code::

    from pharmpy.modeling import write_model
    write_model(model)

Optionally a path can be specified:

.. pharmpy-code::

   write_model(model, path='/home/user/mymodel.mod')


~~~~~~~~~~~~~~~~~~~~~~
Getting the model code
~~~~~~~~~~~~~~~~~~~~~~

The model code can be inspected using :py:func:`print_model_code<pharmpy.modeling.print_model_code>` or retrieved using :py:func:`generate_model_code<pharmpy.modeling.generate_model_code>`.

.. pharmpy-execute::

    from pharmpy.modeling import print_model_code

    print_model_code(model)

~~~~~~~~~~~~~~~~
Model parameters
~~~~~~~~~~~~~~~~

Model parameters are scalar values that are used in the mathematical definition of the model and are estimated when a model is fit from data. The parameters of a model are thus optimization parameters and can in turn be used as parameters in statistical distributions or as structural parameters. A parameter is represented by using the :py:class:`pharmpy.Parameter` class.

.. pharmpy-execute::

   from pharmpy.model import Parameter

   par = Parameter('THETA_1', 0.1, upper=2, fix=False)
   par

A model parameter must have a name and an inital value and can optionally be constrained to a lower and or upper bound. A parameter can also be fixed meaning that it will be set to its initial value. The parameter attributes can be read out via properties.

.. pharmpy-execute::

   par.lower


~~~~~~~~~~~~~~
Parameter sets
~~~~~~~~~~~~~~

It is often convenient to work with a set of parameters at the same time, for example all parameters of a model. In Pharmpy multiple parameters are organized using the :py:class:`pharmpy.Parameters` class as an ordered set of :py:class:`pharmpy.Parameter`. All parameters of a model can be accessed by using the parameters attribute:

.. pharmpy-execute::

   parset = model.parameters
   parset

Each parameter can be retrieved using indexing

.. pharmpy-execute::

   parset['PTVCL']

Operations on multiple parameters are made easier using methods or properties on parameter sets. For example:

Get all initial estimates as a dictionary:

.. pharmpy-execute::

   parset.inits


~~~~~~~~~~~~~~~~
Random variables
~~~~~~~~~~~~~~~~

The random variables of a model are available through the ``random_variables`` property:

.. pharmpy-execute::

   rvs = model.random_variables
   rvs

.. pharmpy-execute::
   :hide-output:

   eta1 = rvs['ETA_1']

Joint distributions are also supported

.. pharmpy-execute::

   from pharmpy.tools import read_modelfit_results

   frem_path = path / "frem" / "pheno" / "model_4.mod"
   frem_model = read_model(frem_path)
   frem_model_results = read_modelfit_results(frem_path)

   rvs = frem_model.random_variables
   rvs

.. pharmpy-execute::

   omega = rvs['ETA_1'].variance
   omega

Substitution of numerical values can be done directly from initial values

.. pharmpy-execute::

   omega.subs(frem_model.parameters.inits)

or from estimated values

.. pharmpy-execute::

   omega_est = omega.subs(dict(frem_model_results.parameter_estimates))
   omega_est

Operations on this parameter matrix can be done either by using SymPy

.. pharmpy-execute::

   omega_est.cholesky()

or in a pure numerical setting in NumPy

.. pharmpy-execute::

   import numpy as np

   a = np.array(omega_est).astype(np.float64)
   a

.. pharmpy-execute::

   np.linalg.cholesky(a)

~~~~~~~~~~~~~~~~~
Model statements
~~~~~~~~~~~~~~~~~

The model statements represent the mathematical description of the model. All statements can be retrieved via the statements property as a :py:class:`pharmpy.Statements` object, which is a list of model statements.

.. pharmpy-execute::

   statements = model.statements
   print(statements)

Changing the statements of a model can be done by setting the statements property. This way of manipulating a model is quite low level and flexible but cumbersome. For higher level model manipulation use the :py:mod:`pharmpy.modeling` module.

If the model has a system of ordinary differential equations this will be part of the statements. It can easily be retrieved from the statement object

.. pharmpy-execute::

   print(statements.ode_system)

Get the amounts vector:

.. pharmpy-execute::

   statements.ode_system.amounts

Get the compartmental matrix:

.. pharmpy-execute::

   statements.ode_system.compartmental_matrix


~~~~~~~~~~~~~~~~~~~
Dependent variables
~~~~~~~~~~~~~~~~~~~

A model can describe one or more dependent variables (output variables). Each dependent variable is defined in the ``dependent_variables`` attribute. This is a dictionary of each dependent variable symbol to the corresponding ``DVID``. If there is only one dependent variable the ``DVID`` column in the dataset is not needed and its value in this definition is unimportant. The expressions of the dependent variables are all found in the statements.

.. pharmpy-execute::

    model.dependent_variables
