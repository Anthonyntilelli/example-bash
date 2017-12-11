# bash_backup - configurable backup wrapper

## Table of Contents
1. [Parameters](#Parameters)
3. [Examples](#Examples)
4. [Exit status](#Exit_status)
5. [Configuration files](#Configuration_files)
6. [Authors](#Authors)

## Parameters:               <a name="Parameters"></a>

  bash_backup -[ioRs]-[B <BID>]


    Action Parameters (choose one)
    -i  Run INITIAL Action
    -o  Run ONGOING Action
    -R  Run RESTORE Action
    -s  Run SHOW    Action
    -h  Prints help message and exits
    Backup ID
    -B  sets backup ID

## Examples:                 <a name="Examples"></a>

`bash_backup -i -B tar_local`

`bash_backup -s -B tar_local`

`bash_backup -o -B tar_local`

`bash_backup -R -B tar_local`

## Exit status:              <a name="Exit_status"></a>

    0  Success
    1  General Failure (varied message)
    3  No entries found for "$CFG_BID:$CFG_ACTION"
    4  Entry "$CONFIG_LINE" is incorrect or more then one line was found
    5  $NUM_OF_ENTRIES entries found in $PRMG_CONFIG_FILE for "$PROGRAM:$ACTION"
    6  $1 is unknown
    7  Unable to use file: "$GL_BACKUP_CONFIG". (Does files exist and is it readable?)
    8  File "$CONFIG" is not ASCII text type"
    9  "$CONFIG" is not owned by root or $USERID (File owner: $config_user)
    10 Wrong permissions on file: $CONFIG.(Is file write/executable by group/other?)
    11 umask is invalid ($SET_UMASK)
    12 More or less then one action set (count: $action_count)
    13 Invalid argument entered -$OPTARG
    14 $OPTARG requires an argument
    15 Unknown remaining command line argument (args: $@ )
    16 -B already set
    17 BID was never set
    18 BID has # in it ($cfg_BID)"
    19 Command Line argument Missing
    20 Could not cd to directory $WORKING_DIR

## Configuration files:      <a name="Configuration_files"></a>
 - Files must be ASCII text, owned by script user or root and only writable by owner
 - Lines starting with '#' are comments
 - Backup and program entries are stored in separate files
 - `GL_BACKUP_CONFIG` determines backup file
 - `GL_PRMG_CONFIG` determines the program file
 -  entries are separated by a new line
 -  Fields in an entry are delimited by a ':'
 -  Fields are case sensitive
 -  Any entry with a default can be omitted.

#### backup entry
`<BID>:<Action>:<Program>:<Arguments>:<Source>:<Backup>:<cd>:<UMASK>`

#### backup fields (examples in `example_config/backup.config`)
 - BID - Name of Backup used to identify, when script is called
 - Action - Name of supported backup action (INITIAL,ONGOING,SHOW,RESTORE).
   Add multiple actions together separated by `,`
 - Program - program used for backup. Must be a program in prgm.config
 - Arguments - list of Arguments to be passed to program. (Default is blank)
 - Source - Path to source of backups. Can be directory or file_name
   (Default is blank)
 - Backup -  Path to backup. Can be directory or file_name (Default is blank)
 - cd - Absolute path to change directory before running backup (Default is /)
 - Umask - Set umask before running program (Default is not to change umask)

#### Program entry (examples in `example_config/prgm.config`)
 All entries begin with `<program>:<action>` rearrange the other fields to make
 program work on command line or omit it

#### Program fields
 - program - program used for backup.
 - action  -  Name of supported backup action (INITIAL,ONGOING,SHOW,RESTORE)
          add multiple actions together separated by `,`
 - arguments -  list of Arguments to be passed to program.
 - source - Path to source of backups. Can be directory or file_name
 - backup - Path to backup. Can be directory or file_name

## Authors:                  <a name="Authors"></a>
- Anthony Tilelli

- Linda Bissum (Mentor)
