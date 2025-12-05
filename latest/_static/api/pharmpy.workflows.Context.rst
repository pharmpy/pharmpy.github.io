Context
=======

.. currentmodule:: pharmpy.workflows

.. autoclass:: Context
   :show-inheritance:

   .. rubric:: Attributes Summary

   .. autosummary::

      ~Context.broadcaster
      ~Context.context_path
      ~Context.dispatcher
      ~Context.model_database
      ~Context.name
      ~Context.ref
      ~Context.seed

   .. rubric:: Methods Summary

   .. autosummary::

      ~Context.abort_workflow
      ~Context.call_workflow
      ~Context.create_rng
      ~Context.create_subcontext
      ~Context.default_exists
      ~Context.exists
      ~Context.finalize
      ~Context.get_model_context_path
      ~Context.get_ncores_for_execution
      ~Context.get_parent_context
      ~Context.get_subcontext
      ~Context.get_top_level_context
      ~Context.has_completed
      ~Context.has_started
      ~Context.list_all_names
      ~Context.list_all_subcontexts
      ~Context.log_error
      ~Context.log_info
      ~Context.log_message
      ~Context.log_warning
      ~Context.retrieve_annotation
      ~Context.retrieve_common_options
      ~Context.retrieve_dispatching_options
      ~Context.retrieve_final_model_entry
      ~Context.retrieve_input_model_entry
      ~Context.retrieve_key
      ~Context.retrieve_log
      ~Context.retrieve_metadata
      ~Context.retrieve_model_entry
      ~Context.retrieve_results
      ~Context.select_context
      ~Context.spawn_seed
      ~Context.store_annotation
      ~Context.store_final_model_entry
      ~Context.store_input_model_entry
      ~Context.store_key
      ~Context.store_message
      ~Context.store_metadata
      ~Context.store_model_entry
      ~Context.store_results

   .. rubric:: Attributes Documentation

   .. autoattribute:: broadcaster
   .. autoattribute:: context_path
   .. autoattribute:: dispatcher
   .. autoattribute:: model_database
   .. autoattribute:: name
   .. autoattribute:: ref
   .. autoattribute:: seed

   .. rubric:: Methods Documentation

   .. automethod:: abort_workflow
   .. automethod:: call_workflow
   .. automethod:: create_rng
   .. automethod:: create_subcontext
   .. automethod:: default_exists
   .. automethod:: exists
   .. automethod:: finalize
   .. automethod:: get_model_context_path
   .. automethod:: get_ncores_for_execution
   .. automethod:: get_parent_context
   .. automethod:: get_subcontext
   .. automethod:: get_top_level_context
   .. automethod:: has_completed
   .. automethod:: has_started
   .. automethod:: list_all_names
   .. automethod:: list_all_subcontexts
   .. automethod:: log_error
   .. automethod:: log_info
   .. automethod:: log_message
   .. automethod:: log_warning
   .. automethod:: retrieve_annotation
   .. automethod:: retrieve_common_options
   .. automethod:: retrieve_dispatching_options
   .. automethod:: retrieve_final_model_entry
   .. automethod:: retrieve_input_model_entry
   .. automethod:: retrieve_key
   .. automethod:: retrieve_log
   .. automethod:: retrieve_metadata
   .. automethod:: retrieve_model_entry
   .. automethod:: retrieve_results
   .. automethod:: select_context
   .. automethod:: spawn_seed
   .. automethod:: store_annotation
   .. automethod:: store_final_model_entry
   .. automethod:: store_input_model_entry
   .. automethod:: store_key
   .. automethod:: store_message
   .. automethod:: store_metadata
   .. automethod:: store_model_entry
   .. automethod:: store_results
