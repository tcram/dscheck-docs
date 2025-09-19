Usage
=====

.. code-block:: bash

    dscheck	[Action Option] [Mode Options] [Info Options]
    dscheck	[-(IF|InputFile)] InputFileNames

Quotes [] indicate optional input options or values. A pipeline '|' in parentheses as in format (A|B) means either A or B can be used. The options applied to **dscheck** are divided into three categories, Action, Mode, and Information (Info for short) options. Action options are used to specify what tasks this utility program to execute, Mode options are used to modify behaviors of the actions, and the Info options are used to pass information, one or multiple values, to run **dscheck**. An option can be given in form of either short name or long name, -DS or -Dataset for example. Some options have alias names for convenience; -UnLock, for example, is an alias option name for Mode option -UL (-UnLockCheck). Option names can be given in either upper or lower cases, while the values following Info options are case sensitive.

Specify one of the Action options each time to execute **dscheck**. Based on what Action is chosen, some of the Info options are mandatory and others are optional and certain Mode options can be applied to alter the behaviors of the Action.

All options, except Info option -IF (-InputFile), can be given either on command line or in input files. Input file names are presented per Info option -IF and can only be provided on command line. Referring to description of Info option -IF (-InputFile) for detail on how to present options in input files. One or multiple input files, combined with options on command line, are allowed to run **dscheck**. The option name, -IF (-InputFile), itself can be omitted if a single input file is given on command line and all other option information are provided inside the input file.

When information of daemons and checks are retrieved, Info options are used to specify conditions for querying information from RDADB. Some special signs can be used to further confine the information with special and complicated conditions; they are '!', '<', '>' and '<>'. These special signs, if provided on command line, must be quoted or escaped to avoid of being interpreted by Unix OS system. The '!', or \!, means exclusion to the following value(s) and it must be the first item following an Info option name, while '<' or '>' mean greater or less than the following value and '<>' means between the following two values. Combine '!' and '<', as syntax "'!' '<' OptionValue", to make a condition of 'larger than or equal to OptionValue'.

Description of an individual option is displayed if **dscheck** is issued on command line as

.. code-block:: bash

    dscheck	[Option] -(h|help) [Option]

A description is displayed for an option given either before or after -(h|help). If no option is specified or **dscheck** is issued by itself, this whole document is displayed per UNIX utility 'more'. A hard copy of this help document can be printed from the saved file: ${DSSHOME}/dssdb/prog_usage/dscheck.usg.

