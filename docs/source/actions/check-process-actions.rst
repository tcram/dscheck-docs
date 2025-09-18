Check Process Actions
======================

Delayed mode command executions recorded in RDADB are automatically started,
or restarted, by the common 'dscheck' daemon. Running commands can be interrupted
at any time and the child processed of the interrupted commands are also cleaned up.
The status of the current check records can be gathered and emailed to a specialist.
  
Here are the actions for process checks:

Process Check
--------------
Start a command from its information recorded in 'dscheck' 

Interrupt Check
---------------
Interrupt a running command for given check record and clean the child processes

Email Check
-----------
Email a specialist for the status of the current check records
