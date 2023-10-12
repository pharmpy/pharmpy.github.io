RandomVariables
===============

.. currentmodule:: pharmpy.model

.. autoclass:: RandomVariables
   :show-inheritance:

   .. rubric:: Attributes Summary

   .. autosummary::

      ~RandomVariables.covariance_matrix
      ~RandomVariables.epsilon_levels
      ~RandomVariables.epsilons
      ~RandomVariables.eta_levels
      ~RandomVariables.etas
      ~RandomVariables.free_symbols
      ~RandomVariables.iiv
      ~RandomVariables.iov
      ~RandomVariables.names
      ~RandomVariables.nrvs
      ~RandomVariables.parameter_names
      ~RandomVariables.symbols
      ~RandomVariables.variance_parameters

   .. rubric:: Methods Summary

   .. autosummary::

      ~RandomVariables.create
      ~RandomVariables.from_dict
      ~RandomVariables.get_covariance
      ~RandomVariables.get_rvs_with_same_dist
      ~RandomVariables.join
      ~RandomVariables.nearest_valid_parameters
      ~RandomVariables.parameters_sdcorr
      ~RandomVariables.replace
      ~RandomVariables.replace_with_sympy_rvs
      ~RandomVariables.sample
      ~RandomVariables.subs
      ~RandomVariables.to_dict
      ~RandomVariables.unjoin
      ~RandomVariables.validate_parameters

   .. rubric:: Attributes Documentation

   .. autoattribute:: covariance_matrix
   .. autoattribute:: epsilon_levels
   .. autoattribute:: epsilons
   .. autoattribute:: eta_levels
   .. autoattribute:: etas
   .. autoattribute:: free_symbols
   .. autoattribute:: iiv
   .. autoattribute:: iov
   .. autoattribute:: names
   .. autoattribute:: nrvs
   .. autoattribute:: parameter_names
   .. autoattribute:: symbols
   .. autoattribute:: variance_parameters

   .. rubric:: Methods Documentation

   .. automethod:: create
   .. automethod:: from_dict
   .. automethod:: get_covariance
   .. automethod:: get_rvs_with_same_dist
   .. automethod:: join
   .. automethod:: nearest_valid_parameters
   .. automethod:: parameters_sdcorr
   .. automethod:: replace
   .. automethod:: replace_with_sympy_rvs
   .. automethod:: sample
   .. automethod:: subs
   .. automethod:: to_dict
   .. automethod:: unjoin
   .. automethod:: validate_parameters
