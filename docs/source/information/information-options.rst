Information Options
===========================

Information options are used to pass information, one or multiple values, into
**dscheck**. Two types of Info options are used:

Single-Value Info Options
--------------------------
Pass a single value to **dscheck**

A single-value Info option is used to pass one value into this application.
One value, and one only, must follow a single-value option; otherwise an
error message is displayed if no value or more than one value passed in.

.. code-block:: bash

    -DM or -DaemonMode

Pass daemon mode values, start, stop, logon or logoff
to **dscheck** Action -PC (-ProcessCheck) to start, to stop, to log detail or
not to log detail, correspondingly.

.. code-block:: bash

    -DV or -Divider (Alias: -Delimiter, -Separator)
    
Delimiter for separating columns of multi-value Info options in input files. 
Default value is ``<:>``.

.. code-block:: bash

    -ES or -EqualSign

For an equal sign of assigning one value to either a single-value option or 
multi-value option in input files. Default is ``<=>``.

.. code-block:: bash

    -FN or -FieldNames

For a string of single letter field names. Values of the selected fields are 
retrieved for check information per actions ``-GC (-GetCheck)``.

.. code-block:: bash

    -LH or -LocalHost

Specify a local hostname to processes checks on the host for action 
``-PC(-ProcessCheck)``. The default is the blank string '' to use 
the local host name. Specify ``PBS`` to process batch jobs.

.. code-block:: bash

    -MT or -MaxrunTime
    
Specify the maxmum run time for deamon mode. The default value is 0 (unlimited 
time). The run time can be specified in seconds or days; for days, specify the 
number followed by a ``D``. For example, ``-MT 5000`` specifies 5000 seconds, 
and ``-MT 1D`` specifies 1 day or 86400 seconds.

.. code-block:: bash

    -OF or -OutputFile

Prints the output to the specified file. If this Info option is not present,
the output is printed to stdout.

.. code-block:: bash

    -ON or -OrderNames
    
For a string of single letter field names use to order the results of getting 
check information via action -GC (-GetCheck).

.. code-block:: bash

    -AO or -ActOption

For setting Action and Mode options in input files. The default is ``<!>``.

.. code-block:: bash

    -WI or -WaitInterval

Set the wait interval between processing input files. The default is 2 minutes (120 seconds). 
It is used as a time interval for the **dscheck** daemon to sleep between processing 
check records.

Multi-Value Info Options
--------------------------
Pass one or multiple values to **dscheck**

A multi-value Info option is used to pass multiple values for one Info option
into **dscheck**. At lease one value must follow each multi-value option.

.. code-block:: bash

    -AN or -ActionName (Alias: -Action)
    
Specifies an action name for given command name recorded in check record.

.. code-block:: bash

    -AV or -ArgumentVector
    
The space delimited argument vector string up to 100 characters. It is quoted
with single quotes '' for a individual argument containing spaces.

.. code-block:: bash

    -AX or -ArgumentExtra
    
The space delimited argument vector string beyond 100 characters. This field 
is not empty only if the argument vector string is longer than 100 characters.

.. code-block:: bash

    -CC or -CarbonCopy
    
Provides additional one or multiple email addresses on command line to send 
Cc'd email notification of the check status. For DECS specialist, login user 
names themselves are acceptable; otherwise full email addresses are required 
for email domains other than 'ucar.edu'.
 
.. code-block:: bash

    -CD or -CheckDate
    
The check date of the recorded command is first processed.
  
.. code-block:: bash

    -CI or -CechkIndex
    
Check record indices for commands recorded in RDADB. A check
record is automatically purged if the command is finished.

.. code-block:: bash

    -CM or -Command (Alias: -CommandName)
    
The command name recorded in check record.

.. code-block:: bash

    -CT or -CheckTime
    
The check time of the recorded command is first processed.
  
.. code-block:: bash

    -DB or -Debug
    
Turns on debug mode with specified information. This option
provides up to 3 values, they are Debug Level, debug log file path and debug
log file name. The debug level is mandatory for this option. It can be a
single integer value, for example, 1000 means to log debug messages for debug
levels 1 to 1000; or a range of values, for example, 200-1000 means to log
debug messages from debug levels 200 to 1000. The default debug file path is
'$DSSHOME}/dssdb/log' and the default debug file name is 'mydss.dbg'. Provides
the second and third values for this option to override the default ones
respectively.

.. code-block:: bash

    -DC or -DoneCount
    
The number of files that are processed successfully already.

.. code-block:: bash

    -DF or -DownFlags
    
Storage system down flags. The current supported flags are:
``H-HPSS``, ``D-DRDATA``, ``G-GLADE``, ``O-ObjectStore``. It can hold multiple flags, up to 5,
for all down storage systems.

.. code-block:: bash

    -DI or -DaemonIndex
    
Daemon control indices. A daemon control record retains
configuration information for how many processes on what host and its priority
can a command be started for specified specialist.

.. code-block:: bash

    -DS or -Dataset
    
For dataset numbers, or called dataset IDs in form as [a-z]NNNNNN.

.. code-block:: bash

    -ER or -ErrorMessage
    
Error message of a failed check command.
 
.. code-block:: bash

    -EV or -Environments, (Alias: -Envs)
    
Specifies environment variables, in form of 
VarName=VarValue and separated by ',', needed to be set to execute a command as
a batch job. The environment varaibles will be set in the batch starting script.

.. code-block:: bash

    -FC or -FileCount
    
The number of files to be processed by a check command.
  
.. code-block:: bash

    -HN or -HostName
    
Specify the host names the check can or cannot be processed on.

.. code-block:: bash

    -IF or -InputFile
    
For input file names; one or multiple file names may be
given on command line. Input files are used to hold all valid options and
the associated values of Info options that need to be passed in for
execution of 'dscheck'.

In a input file, lines start with sign '#' are considered as comments;
Option Names can be given either short, long or alias names. Action and Mode
options are given in format of OptionName<!>. Single value Assignment is 
given in format of OptionName<=>OptionValue. One option is given on each line.
Different setting sign of Action and Mode options can be provided by Info
option -AO (-ActOption, default to <!>); and different equal sign of single
value assignment can be provided by Info option -ES, (-EqualSign, default to
'<=>'). Multi-value assignments can be given in columns delimited with
separator specified per option -SP (-Separator, default to '<:>'). It starts
with a column title line for multi-value option names and the rest holds
values corresponding to each column titles. The value information stops at
the end of the file or when a new column name line or another single value
assignment appears. If the last column is a multi-line value field, an
additional separator must be appended for each line, including the column
title line to end lines properly.

.. code-block:: bash

    -MC or -MaxCount
    
The maximum number of tries for a check command can be processed
if the command is failed.

.. code-block:: bash

    -MH or -MatchHost (Alias: -MatchHostname)

Flag to control hostname match. 'G' - general match, including empty hostname 
specified, or exclusive hostnames given but the hostname is not in the list, 
and 'M' - match only the hostname specified is identical to the current host.

.. code-block:: bash

    -MO or -Modules, (Alias: -Mods)
    
Specifies module names, separated by ',',
needed to be loaded to execute a command as a batch job. The modules will
be set in the batch starting script.

.. code-block:: bash

    -PI or -ParentIndex
    
Specifies a parent check index for the current check to wait on.

.. code-block:: bash

    -PO or -Priority
    
Specifies the priority of a given host so that the host is 
picked in such an order to start a 'dscheck' process.

.. code-block:: bash

    -PL or -ProcessLimit
    
Specifies how many processes can be started for specified
command and specialist on a given host; Work for Action -SO (-SetOptions) to limit
how many concurrent cron processes.

.. code-block:: bash

    -PQ or -PBSQueue
    
Specifies PBS batch queue index the current check to submit to.

.. code-block:: bash

    -QS or -QsubOptions, (Alias: -PBSOptions)
    
Specifies options to execute a command
as a batch job via qsub on PBS nodes. The qsub options must be quoted when prsented
on command line, such as, -QS '-l walltime=12:00:00'.
  
.. code-block:: bash

    -SN or -Specialist
    
The specialist who runs the original command. This Info
option is working with Action -GC (-GetCheck) only to view check information
of a specified specialist.
 
.. code-block:: bash

    -ST or -Status
    
Check command status for a check record. Include command
progress percentage if under process and error message for a failed command.
  
.. code-block:: bash

    -SZ or -DataSize
    
The total bytes of data is processed for the check record.

.. code-block:: bash

    -TC or -TryCount
    
The number of tries for a check command being processed. It
is up to the number of tries specified via info option -MC. 
  
.. code-block:: bash

    -WD or -WorkDir (Alias: -WorkDirectory)
    
The working directory where the recorded command is started.