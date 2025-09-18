Daemon Control Actions
======================

A daemon control record for a command, a specialist and a hostname is used to
configure how many concurrent processes the specified command can be executed
for the specialist on specified hostname, and the priority the the hostname is
picked to start the command. A running centralized daemon reads this record
periodically in case the configuration is changed while the daemon is still
running, so that specialists can reset the values in daemon control records to
change the behavior of dscheck daemon dynamically without shutting the daemon down.

Daemon control information can be created, modified and viewed via Actions
included in this section:

Set Daemon Control
-------------------
Create and modify daemon control information for specified specialists, commands and hostnames

-SD or -SetDaemon, creates and modifies daemon control information into
RDADB for given specialist login names, commands, and hostnames of computers on
which the check commands are processed. One or multiple records can be set each
time.

.. code-block:: bash

    dscheck -(SD|SetDaemon) [Mode Option]
         [-(DI|DaemonIndex) controlIndices]
         [-(CM|Command)  UtilityProgramNames]    # ALL for any command names
         [-(SN|Specialist) DECSSpecialists]
         [-(HN|HostName)  HostMachineNames]
         [-(MH|MatchHost)  FlagToMatchHostname]
         [-(PL|ProcessLimit) MaxNumberOfProcesses],
         [-(PO|Priority) HostListOrder]


Mode option that can be specified for this action include:
-(ND|NewDaemon) - sets a new daemon control record into RDADB

If information of a daemon control exists already in RDADB for a given specialist,
a command and a hostname, the daemon control record is modified; otherwise, a new
daemon control record is added if daemon index is 0 and Mode option -ND (-NewDaemon)
is present. Combination of specialist login name, command name and hostname of
computer must be unique for each daemon control record.

Specify host name 'SLURM' for putting the command in the SLURM batch control system. If
a specified command name is not found in the daemon control, the general 'dscheck'
configuration for command name 'ALL' is used.
  
For example, set daemon control information for schuster, all commands on SLURM hosts,
for maximum 4 checks can be processed at the same time with priority 1, the smaller
the number the higher the priority is, via input file daemon.ctl

  dsrqst SD -ND -IF daemon.ctl

.. code-block:: bash

    Content of input file daemon.ctl
    DaemonIndex<:>Command <:>Specialist<:>Hostname<:>ProcessLimit<:>Priority<:>
    0          <:>schuster<:>ALL       <:>SLURM   <:>4           <:>1       <:>


Get Daemon Control
-------------------
Retrieve information of existing daemon controls

-GD or -GetDaemon, retrieves daemon control information for given commands,
specialists or hostnames. Daemon control information of specified specialists
are retrieved if the specialist login names are provided. Without specified
condition, only the daemon control records set for the specialist who runs
**dscheck** are retrieved.

.. code-block:: bash

  dscheck -(GD|GetDaemon) [Mode Option]
         [-(FN|FieldNames) FieldNameString]
         [-(DI|DaemonIndex) controlIndices]
         [-(CM|Command) UtilityProgramNames]
         [-(SN|Specialist) DECSSpecialists]
         [-(HN|HostName)  HostMachineName]
         [-(PL|ProcessLimit) MaxNumberOfProcesses]
         [-(PO|Priority) ProcessPriority]
         [-(OF|OutputFile) OutputFileName] 
         [-(DB|Debug) DebugModeInfo]

Mode option that can be specified for getting check control Action:
-(FO|FormatOutput) - format the column output with a fix width for all values
                       of a given field

Use Info option -FN (-FieldNames) to specify what daemon control fields to be
retrieved. It defaults to all available fields if option -FN is not provided.

Valid field names of daemon controls and their corresponding Info option
names:

  Names  Info Options           Descriptions
  I      -(DI|DaemonIndex)      daemon control index
  C      -(CM|Command)          command names of utility programs
  H      -(HN|Hostname)         computer hostname
  M      -(MH|MatchHost)        Flage to control hostname match
  S      -(SN|Specialist)       DECS specialist the daemon set for
  P      -(PL|ProcessLimit)     Max check count to be processed at the same times
  O      -(PO|Priority)         host priority a specified command to start on
  
Daemon control information can be retrieved for specified specialist per option
-SN (-Specialist), and/or other conditions. Info option -SN, -CM and -HN accept
wildcard input of '%' for matching any number of characters. 

If daemon control index is not given, 'dscheck' gathers only the daemon control
records owned by the specialist who executes this getting daemon control Action.
To view daemon control records owned by another specialist, you need specify Info
option -SN (-Specialist). To view all control records, you simply provide option
-SN with value of 'ALL'.
  
For example, to get all daemon control information currently set for you
  
.. code-block:: bash

  dscheck GD

Delete Daemon Control
----------------------
Delete one or multiple daemon control records

-DL or -Delete (Alias: -RM, -Remove), deletes one or multiple daemon control records
from RDADB for given daemon control indices. 

.. code-block:: bash

  dscheck -(DL|Delete)
          -(DI|DaemonIndex) DaemonControlIndices
         [-(DB|Debug) DebugModeInfo]

Use this action to delete daemon control information. Delete a daemon
control record to remove the daemon specific configuration for a command,
a specialist and a hostname.
