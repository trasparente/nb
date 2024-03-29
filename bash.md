# bash
`echo $SHELL` to print the shell

## source file
- `. ~/.bashrc`

## history
- `history` list
- `!!` execute last command
- `!n` execute command n

## filesystem
- `mv <SOURCE> <DEST>` rename files and folders

## shortcuts
- `ctrl l` clear console
- `ctrl a` move beginning of line
- `ctrl k` cut from cursor to end of line
- `ctrl y` paste last cut text

## infos

### screen
- `tput cols` screen columns
- `tput lines` screen lines

## scripts
- `#!/bin/bash` header for scripts
- `chmod +x script.sh` make executable

### functions

- `$#` arguments number
- `$@` whole arguments
- `$N` arguments N=1, 2, 3...
- `$0` script name

## focal fossa upgrade

### wired network

- `cd r8168-8-049.02` cd inside
- `sudo ./autorun.sh` install
- `lsmod | grep r8168` verify
- `ifconfig -a` verify

### sound and keyboard

- `sudo apt install linux-modules-extra-$(uname -r)` install
