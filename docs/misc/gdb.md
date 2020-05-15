# GDB - GNU Debugger

## installing gdb

    sudo apt-get update
    
    sudo apt-get install gdb

## gdb command

Please note that the program/application being debugged must have been compiled using *-g* flag. 

In complex project which employ *cmake* and *make* based toolchains, enabling debug option may require setting some additional flags.

1. To start the debugger

    gdb <prog_name>

2. Setting breakpoints

set a breakpoint at line number 2 of main.c

    break main.c:2

set a breakpoint at the beginning of a function *f1()*

    break  f1

10. To quit gdb

     quit


     