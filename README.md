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

## Exit status:
<a name="Exit_status"></a>

    0   Success
    1   General Failure (varied message)
    3   No "$Entry_NAME:$ACTION" found in backup.config
    4   Multple entries found in $GLOBAL_BACKUP_CONFIG
# old

  4   "Requires shell parameters to run"
  5   Error code for backup functions (varied message)
  6   "User configuration file is not owned specified user [uid]"
  7   "Unable to use file:\"$CONFIG\". (Does files exist and is it readable?)"
  8   "Wrong permissions on file: [CONFIG_file]. (Is file write/executable by group or other?)"
  9   "Function missing from Config [ PASSED_VALUE: $PASSED_VALUE ]"
  10  "No usable configuration found"
  11  "Backup Mode already set
  12  "User or System config not chosen"
  13  "Invalid argument entered -$OPTARG"
  14  "$OPTARG requires an argument"
  15  "Invalid Configuration file(s) Chosen"
  16  "-e already set"
  17  "-e argument must start with \"=\" OPTARG: $OPTARG is invalid"
  18  "Backup mode was never chosen"

## Configuration files:      <a name="Configuration_files"></a>
 - back.config - backup entry lists
 - prgm.config - program usage configuration


## Configuration functions:  <a name="Configuration_functions"></a>

## Authors:                  <a name="Authors"></a>
- Anthony Tilelli

- Linda Bissum (Mentor)
