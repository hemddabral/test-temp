# This document lists some handy unix commands

## wget

*wget url* e.g. follwoing:

    wget https://nodejs.org/download/release/latest-erbium/node-v12.16.3-linux-x64.tar.gz

you can use *--no-check-certificate* if security errors occcur.


## extracting a .gz *gunzip* file

    tar -zxvf filename.gz

## find - search for files in a directory

    find <directory_name> -name <file_name>

## grep - global regular expression print

very useful for searching patterns and regular expressions in files.

usefull flags for grep command:

recursive: *-r*
case insensitive: *-i*

    grep -r -i -n <pattern> <directory>

search for selective file extensions:

     grep -rin 'CORE_RING_BUFFER_OBJ_DECLARE' --include=\*.c folder_name

## using pipe

    cat test_lcut_main.c | grep -irn 'test_lcut_core_ring_buffer'

    



