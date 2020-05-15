# Bash Scripts

The name is an acronym for the *Bourne-Again SHell*
A Bash script tells *Bash shell* about a series of operations which are to be performed.

tutorial [at](https://ryanstutorials.net/bash-scripting-tutorial/bash-script.php)

## Format of a bash script

### First line is always *shebang* character

    #!/bin/bash

### comments in a script

comments in a script start with *#*, e.g.

    # This is a comment

## Variables

- variables can be declared anywhere in the script.

- when referring to a variable, prefix its name with $

- when setting value of a variable $ is not needed.

### Important Note

There should not be any space between variable name, =, and vaiable value.**
    
    my_variable=10

## command line arguments

$0 refers to name of the bash script.

$1 refers to first command line argument, $2 to second, $3 to third and so on.






