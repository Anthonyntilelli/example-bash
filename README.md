# custom_backup - configurable backup wrapper

## Table of Contents
1. [Overview](#Overview)
2. [Parameters](#Parameters)
3. [Examples](#Examples)
4. [Exit status](#Exit_status)
5. [Configuration files](#Configuration_files)
6. [Configuration functions](#Configuration_functions)
7. [Authors](#Authors)

## Overview:                 <a name="Overview"></a>

## Parameters:               <a name="Parameters"></a>

## Examples:                 <a name="Examples"></a>

## Exit status:              <a name="Exit_status"></a>

    0  Success
    1  General Failure (varied message)
    3  $NUM_OF_ENTRIES entries found in $GLOBAL_BACKUP_CONFIG for "$Entry_NAME:$ACTION"
    4  Entry "$CONFIG_LINE" is incorrect
    5  $NUM_OF_ENTRIES entries found in $GL_PRMG_CONFIG for "$Gl_cfg_Program:$Gl_cfg_Action"
    6  $entry is unknown (col: $col)
    7  Unable to use file: "$GL_BACKUP_CONFIG". (Does files exist and is it readable?)
    8  File "$CONFIG" is not ASCII text type"
    9  "$CONFIG" is not owned by root or $USERID (File owner: $config_user)
    10 Wrong permissions on file: $CONFIG.(Is file write/executable by group/other?)
    11 umask is invalid ($SET_UMASK)
    12 More or less then one action set (count: $action_count)
    13 Invalid argument entered -$OPTARG
    14 $OPTARG requires an argument
    15
    16 -B already set
    17 -B argument must start with `=` OPTARG: $OPTARG is invalid
    18 BID has # in it ($cfg_BID)"

## Configuration files:      <a name="Configuration_files"></a>
Files must be ASCII text, owned by script user or root and only writable by owner

 - back.config - backup entry lists
 - prgm.config - program usage configuration




## Configuration functions:  <a name="Configuration_functions"></a>

## Authors:                  <a name="Authors"></a>
- Anthony Tilelli

- Linda Bissum (Mentor)
