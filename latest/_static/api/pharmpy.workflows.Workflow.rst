Workflow
========

.. currentmodule:: pharmpy.workflows

.. autoclass:: Workflow
   :show-inheritance:

   .. rubric:: Attributes Summary

   .. autosummary::

      ~Workflow.input_tasks
      ~Workflow.output_tasks
      ~Workflow.tasks

   .. rubric:: Methods Summary

   .. autosummary::

      ~Workflow.add_task
      ~Workflow.as_dask_dict
      ~Workflow.copy
      ~Workflow.get_predecessors
      ~Workflow.get_successors
      ~Workflow.get_upstream_tasks
      ~Workflow.insert_workflow
      ~Workflow.plot_dask

   .. rubric:: Attributes Documentation

   .. autoattribute:: input_tasks
   .. autoattribute:: output_tasks
   .. autoattribute:: tasks

   .. rubric:: Methods Documentation

   .. automethod:: add_task
   .. automethod:: as_dask_dict
   .. automethod:: copy
   .. automethod:: get_predecessors
   .. automethod:: get_successors
   .. automethod:: get_upstream_tasks
   .. automethod:: insert_workflow
   .. automethod:: plot_dask
