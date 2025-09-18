Introduction
============

**dscheck** is a utility to add, remove, view and process recorded commands of other utility programs in Research Data Archive Management System (RDAMS). For delayed execution, or called batch process, of utility programs, **dsarch**, **dsupdt** and **dsrqst**, the commands information and the directories where the commands are initiated are saved into RDADB as check records. For any other specialist-defined commands, they can be also put in delayed mode if the commands are added to **dscheck** control via Action -AC (-AddCheck).

The check records are processed automatically via a centralized **dscheck** daemon, although they can be processed manually on command line. During the execution of a recorded command, the check record is locked in RDADB to prevent multiple executions of the same command. The check records that retain command information are automatically purged into check history when the commands are finished.

When a recorded command fails due to failures of computer system, storage disk/tape, or the Database Management System, the check record is normally purged with status 'E' for error, unless check-reprocessing ability is built into the utility program, such as **dsarch**. For a check-reprocessing command, the check record is retained in RDADB Until the command is processed successfully or the number of executions reaches the try limits allowed. Utility programs **dsrqst** and **dsupdt** carry their own failure- recovering ability and they do not need check-reprocessing.

The purged check records are retained in RDADB. The check history can be viewed via utility program **viewcheckusage**.

Program **dscheck** supports the following major functions:

* Set daemon control records for individual specialists to configure how many concurrent processes of a specified command can be executed on a given host, and the host priorities to define the order of which host is picked for processing a check. Without the daemon control information, a recorded command will not be started automatically.
* Add a check record for delayed command execution of any specialist-defined commands
* View utility command information currently saved in RDADB
* Email the current status of a specified utility command or a list of commands, and include error messages if any, to a specialist
* Delete recorded command information, because the command is not needed anymore
* Unlock a given recorded command in case lock information was not cleaned properly when the command was failed
* Interrupt a utility command that is under execution and kill recursively all the associated child processes
* Add the due 'dsrqst' and 'dsupdt' actions into dscheck records
* Process commands that have been recorded into RDADB or the ones have failed previously.

The specialist who executes a utility command under **dscheck** control remains the exclusive owner of the check record in RDADB. This prevents the command to be processed or deleted accidentally by other specialists.

In the following sections, general usages of **dscheck** are described first; and detail descriptions of Action options are given; and finally Mode and Info options are explained.

