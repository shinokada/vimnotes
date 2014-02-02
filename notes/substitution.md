# Substitution

[Vim 101: Search and Replace](http://usevim.com/2012/03/30/search-and-replace/)

## Search and replace

    # first match on the current line
    :s/search/replace/
    # all matches on the current line
    :s/search/replace/g
    # every match in the file
    :%s/search/replace/g # % is the same as 1,$
    # search and replace by line numbers
    :100,200s/search/replace/g
    # case insensitive with i
    :%s/search/replace/gi
    # confirm each match with c
    :%s/search/replace/gic

## options for confirm

    y               Yes; make this change.
    n               No; skip this match.
    a               All; make this change and all remaining ones without
                    further confirmation.
    q               Quit; don't make any more changes.
    l               Last; make this change and then quit.
    CTRL-E          Scroll the text one line up.
    CTRL-Y          Scroll the text one line down.

## Using register 

    # substitute with the content of register a
    :%s/search/<C-r>a/g

## Substitution with multiple files

    # open multiple files
    vim *.js
    # list the buffers
    :ls
    
