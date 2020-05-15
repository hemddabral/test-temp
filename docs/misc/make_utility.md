# make

complete documentation can be found [at](https://www.gnu.org/software/make/manual/make.html#Reading)

## makefile

make utility requires *makefile* as input. makefile tells *make* what to do.

# rules in makefile

    target … : prerequisites …
        recipe
        …
        …

## note: 

- there must be a TAB character at the begining of rule in the recipe.
- by default *make* starts with first target when called without passing any target as argument.
- *make* works on *makefile* present in currnet directory


