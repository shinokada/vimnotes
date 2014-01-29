# Files

## Track open files with the buffer list

    $ cd code/files
    $ vim *.txt
    # only one file is visible
    # run to see other files
    :ls
    # switch to the next buffer
    :bnext
    :ls

`%` symbol indicates which of the buffers is visible in the current window. `#` symbol represents the alternate file. 
We can toggle between the current and alternate files by `<C-^>`, on Mac `<C-6>`.

