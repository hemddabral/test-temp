# vim 

## vim configuration file

vim's global settings are installed in */etc/vim/vimrc* file. You can write configurations in this directory, and they will be applied always when *vim* is launched.

## useful commands

1. Jump directly to a line number immediately after opening a file

    // following command opens <file_name> and jumps to line number 100
    vim +100 <file_name>

2. copy 

yw: copy to the start of next word
yiw: copy current word

yy: copy current line
3yy: copy three lines starting from current line

y$: copy till the end of line



3. to run unix shell commands from vim

:!<unix_command>

4. search for text

    :/<text_to_search>

*n* for next occurrence, *N* for previous occurrence

