========================
Reading modelfit results
========================

Pharmpy can retrieve results from a NONMEM run.

.. math::

~~~~~~~~~~~~~~~~
Modelfit results
~~~~~~~~~~~~~~~~

Final OFV
~~~~~~~~~

The final OFV is available in `ofv`:

.. pharmpy-execute::

    from pharmpy.modeling import read_model

    model = read_model('tests/testdata/nonmem/pheno_real.mod')
    model.modelfit_results.ofv


Parameter estimates
~~~~~~~~~~~~~~~~~~~

The `parameter_estimates` series contains the final estimates of all estimated parameters.

.. pharmpy-execute::

    model.modelfit_results.parameter_estimates

It is also possible to get the parameters with all variability parameters as standard deviations or correlations.

.. pharmpy-execute::

   model.modelfit_results.parameter_estimates_sdcorr

Standard errors of parameter estimates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The standard errors of the parameter estimates are in the `standard_errors` series.

.. pharmpy-execute::

    model.modelfit_results.standard_errors

Or in `standard_errors_sdcorr` with variability parameters as standard deviations or correlations.

.. pharmpy-execute::

    model.modelfit_results.standard_errors_sdcorr

Relative standard errors of parameter estimates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The relative standard errors of the parameter estimates


.. pharmpy-execute::

    model.modelfit_results.relative_standard_errors

Covariance matrix
~~~~~~~~~~~~~~~~~

The covariance matrix for all estimated parameters

.. pharmpy-execute::

    model.modelfit_results.covariance_matrix

Correlation Matrix
~~~~~~~~~~~~~~~~~~

The correlation matrix for all estimated parameters.

.. note::
    Note to NONMEM users. This is a proper correlation matrix meaning that diagonal elements are 1.
    Standard errors can be retrieved from `standard_errors`.

.. pharmpy-execute::

    model.modelfit_results.correlation_matrix

Information Matrix
~~~~~~~~~~~~~~~~~~

The information matrix for all estimated parameters. This is the inverse of the covariance matrix.

.. pharmpy-execute::

    model.modelfit_results.information_matrix

Indiviudal OFV
~~~~~~~~~~~~~~

The OFV for each individual or `iOFV` is in the `individual_ofv` series.

.. pharmpy-execute::

    model.modelfit_results.individual_ofv

Predictions
~~~~~~~~~~~

Different predictions can be found in `predictions`

.. pharmpy-execute::

    model.modelfit_results.predictions

Residuals
~~~~~~~~~

Different residual metrics can be found in `residuals`

.. pharmpy-execute::

    model.modelfit_results.residuals

Individual estimates
~~~~~~~~~~~~~~~~~~~~

Individual estimates (or EBEs)

.. pharmpy-execute::

    model.modelfit_results.individual_estimates

Uncertainty for the individual estimates can be found in `individual_estimates_covariance`, which is a series of covariance matrices for each individual.

.. pharmpy-execute::

    model.modelfit_results.individual_estimates_covariance[1]
