Daemon Control Actions
======================

A daemon control record for a command, a specialist and a hostname is used to
  configure how many concurrent processes the specified command can be executed
  for the specialist on specified hostname, and the priority the the hostname is
  picked to start the command. A running centralized daemon reads this record
  periodically in case the configuration is changed while the daemon is still
  running, so that specialists can reset the values in daemon control records to
  change the behave of dscheck daemon dynamically without shutting the daemon down.

  Daemon control information can be created, modified and viewed via Actions
  included in this section:
     Set Daemon Control - create and modify daemon control information for specified
                          specialists, commands and hostnames
     Get Daemon Control - retrieve information of existing daemon controls
  Delete Daemon Control - delete one or multiple daemon control records