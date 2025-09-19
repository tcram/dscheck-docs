Action options
================

Action options are used to specify what task **dscheck** executes. No values
are allowed to follow Action options. Multiple Action options provided
simultaneously are blocked.

Based on the information being manipulated, the actions are divided into three
categories:

.. topic:: Daemon Control Actions

    Create, delete, modify and view daemon control information in RDADB, of specified specialist, command and hostname

.. topic:: Check Actions

    Add, delete, unlock and view check information of the active individual checks

.. topic:: Check Process Actions

    Process checks by starting commands on remote hosts as configured in daemon controls and purge checks by recording the commands and their execution information into check history; interrupt the current executing commands by killing the current process and its all children; and email status of current checks

.. toctree::
   :caption: Action Categories
   :maxdepth: 2
   :titlesonly:

   daemon-control-actions
   check-actions
   check-process-actions
   daemon-host-connectivity
   set-batch-options
