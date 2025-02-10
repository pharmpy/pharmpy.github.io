Statements
==========

.. currentmodule:: pharmpy.model

.. autoclass:: Statements
   :show-inheritance:

   .. rubric:: Attributes Summary

   .. autosummary::

      ~Statements.after_odes
      ~Statements.before_odes
      ~Statements.error
      ~Statements.free_symbols
      ~Statements.lhs_symbols
      ~Statements.ode_system

   .. rubric:: Methods Summary

   .. autosummary::

      ~Statements.create
      ~Statements.dependencies
      ~Statements.direct_dependencies
      ~Statements.find_assignment
      ~Statements.find_assignment_index
      ~Statements.from_dict
      ~Statements.full_expression
      ~Statements.get_assignment
      ~Statements.reassign
      ~Statements.remove_symbol_definitions
      ~Statements.subs
      ~Statements.to_dict

   .. rubric:: Attributes Documentation

   .. autoattribute:: after_odes
   .. autoattribute:: before_odes
   .. autoattribute:: error
   .. autoattribute:: free_symbols
   .. autoattribute:: lhs_symbols
   .. autoattribute:: ode_system

   .. rubric:: Methods Documentation

   .. automethod:: create
   .. automethod:: dependencies
   .. automethod:: direct_dependencies
   .. automethod:: find_assignment
   .. automethod:: find_assignment_index
   .. automethod:: from_dict
   .. automethod:: full_expression
   .. automethod:: get_assignment
   .. automethod:: reassign
   .. automethod:: remove_symbol_definitions
   .. automethod:: subs
   .. automethod:: to_dict
