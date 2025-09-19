Mode Options
================

Use proper Mode options to modify behaviors of Action options. Mode options
are all optional. No value is allowed to be passed in following any Mode option.

  ``-AW`` or ``-AnyWhere`` 
  
  for Action -AC (-AddCheck), sets Working directory empty in
  check record to start processing the check anywhere.

  ``-BG`` or ``-BackGround`` (Alias: ``-b``)
  
  background process. When it presents
  screen display is turned off for both standard outputs and errors. ``-(CP|CheckPending)`` - Check and kill long pending checks

  ``-CP`` or ``-CheckPending``
  
  if present for Action -PC (-ProcessCheck), check and kill
  long pending checks

  ``-CS`` or ``-CheckStatus``
  
  if present, displays detailed status information of the
  recorded commands, including progress percentage for a running command and
  error message for a failed command.

  ``-FI`` or ``-ForceInterrupt``
  
  if present, force interrupts a check that is still under
  processing; otherwise a warning message will display.

  ``-FO`` or ``-FormatOutput``
  
  if present, formats column output results for get
  actions. A same width, evaluated dynamically, is applied for all values of a
  given field.

  ``-LO`` or ``-LogOn`` (Alias: ``-LoggingOn``)
  
  turns detail logging on when 'dscheck' starts
  in Daemon mode. The detail logging is off as default if this Mode option is
  not present.

  ``-MD`` or ``-MyDataset``
  
  allows a specialist to manipulate check information of
  a given dataset listed for another specialist.

  ``-NC`` or ``-NoCommand`` (Alias: ``-NoRemoteCommand``)
  
  does not issue remote commands if
  this Mode option is present for action -PC (-Processcheck).

  ``-ND`` or ``-NewDaemon``
  
  a new daemon control can only be added when this Mode option is
  present and daemon control index is given as 0 when Action -SD (-SetDaemon) of
  'dscheck' is executed. This Mode option blocks mistakes of adding daemon control
  records unintentionally.

  ``-NT`` or ``-NoTrim``
  
  skips trimming of spaces and comments from input values to
  speed up reading input file(s).

  ``-WR`` or ``-WithdsRqst``
  
  adds requests due to be built or purged of command 'dsrqst'
  for 'dscheck' Action -PC (-ProcessCheck) in non-daemon mode.

  ``-WU`` or ``-WithdsUpdt``
  
  adds due update controls of command 'dsrqst' for 'dscheck'
  Action -PC (-ProcessCheck) in non-daemon mode.
