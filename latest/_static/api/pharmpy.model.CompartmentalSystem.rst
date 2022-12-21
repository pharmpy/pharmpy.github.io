CompartmentalSystem
===================

.. currentmodule:: pharmpy.model

.. autoclass:: CompartmentalSystem
   :show-inheritance:

   .. rubric:: Attributes Summary

   .. autosummary::

      ~CompartmentalSystem.amounts
      ~CompartmentalSystem.central_compartment
      ~CompartmentalSystem.compartment_names
      ~CompartmentalSystem.compartmental_matrix
      ~CompartmentalSystem.dosing_compartment
      ~CompartmentalSystem.free_symbols
      ~CompartmentalSystem.output_compartment
      ~CompartmentalSystem.peripheral_compartments
      ~CompartmentalSystem.rhs_symbols
      ~CompartmentalSystem.t
      ~CompartmentalSystem.zero_order_inputs

   .. rubric:: Methods Summary

   .. autosummary::

      ~CompartmentalSystem.atoms
      ~CompartmentalSystem.create
      ~CompartmentalSystem.find_compartment
      ~CompartmentalSystem.find_depot
      ~CompartmentalSystem.find_transit_compartments
      ~CompartmentalSystem.get_compartment_inflows
      ~CompartmentalSystem.get_compartment_outflows
      ~CompartmentalSystem.get_flow
      ~CompartmentalSystem.get_n_connected
      ~CompartmentalSystem.replace
      ~CompartmentalSystem.subs
      ~CompartmentalSystem.to_compartmental_system
      ~CompartmentalSystem.to_explicit_system

   .. rubric:: Attributes Documentation

   .. autoattribute:: amounts
   .. autoattribute:: central_compartment
   .. autoattribute:: compartment_names
   .. autoattribute:: compartmental_matrix
   .. autoattribute:: dosing_compartment
   .. autoattribute:: free_symbols
   .. autoattribute:: output_compartment
   .. autoattribute:: peripheral_compartments
   .. autoattribute:: rhs_symbols
   .. autoattribute:: t
   .. autoattribute:: zero_order_inputs

   .. rubric:: Methods Documentation

   .. automethod:: atoms
   .. automethod:: create
   .. automethod:: find_compartment
   .. automethod:: find_depot
   .. automethod:: find_transit_compartments
   .. automethod:: get_compartment_inflows
   .. automethod:: get_compartment_outflows
   .. automethod:: get_flow
   .. automethod:: get_n_connected
   .. automethod:: replace
   .. automethod:: subs
   .. automethod:: to_compartmental_system
   .. automethod:: to_explicit_system
