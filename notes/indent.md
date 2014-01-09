# Indent

[VimTip224](http://vim.wikia.com/wiki/VimTip224)

In php+html I found the following is good for me.

    :set ft=html # Change the file type to html
    =G # to indent all lines 
    :set ft=phtml # Change the file type to phtml
    =G # to indent all php lines

    # to indent the current line
    >> # << to unindent
    5>>.. # shifts five lines to the right 

`5>>` will indent depends on your set shiftwidth=2. With this setting first it will move 2 spaces to right. 
Then `..` will repeat twice. The total shift will be 6.

In insert mode, `Ctrl-t` indents the current line and `Ctrl-d` to unindent.

    v # visual mode
    jj # select 3 lines
    > # indent
    . # repeat
    gv # to reselect

    3>> # to shift right 3 lines
    >2j # to shift right 3 lines

## Indent an entire buffer

    gg=G

## `==` and `=`

In normal mode `==` indents the current line. 

