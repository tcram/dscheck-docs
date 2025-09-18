Set Batch Options Dynamically
==================================================

The `SetBatchOptions` action, invoked with the command line option
``-SO`` or ``-SetOptions`` (Alias: ``-SetBatchOptions``), processes batch options with
a leading '!' to build options dynamically.

Usage
-----

.. code-block:: console

  dscheck -(SO|SetOptions)
         [-(HN|HostName) HostNames]
         [-(PL|ProcessLimit) MaxNumberOfProcesses]
         [-(MO|Modules)  ModuleList]
         [-(EV|Environments)  EnvironmentPairList]
         [-(QS|QsubOptions)  PBSBatchOptions]
         [-(DB|Debug) DebugModeInfo]