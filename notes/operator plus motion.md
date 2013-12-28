# Operator plus Motion

Notes taken from Practical Vim by Drew Neil

## Operators

    c,d,y,gU
    g~ # swap case
    gu # make lowercase
    ! # filter(motion) lines through an external program
    = # Autoindent
    < # shift left
    > # shift right

## Operator+motion

    gUaw # to convert the current word to uppercase.
    dap # delete a paragraph
    gUap # Make a paragraph to uppercase


## Duplicate act on the current line.

    dd # delete the line
    >> # indent the line
    gUgU # or gUU to uppercase the line

## tpope/vim-commentary

This comments and uncomments as well. Use `.` for repeating.

    3\\j # comment out 3 lines below including the current line
    4\\k # comment out 4 lines above including the current line
    \\ap # or gcap tocomment out a paragraph
    \\G # comment out the current line to the end of the file
    \\\ # or gcc to comment the current line
    gcu # to uncomment


## kana/vim-textobj-entire

    gg=G # autoindent the entire file
    # if you have vim-textobj-entire
    =ae # or =ie
    # if you have vim-textobj-entire and vim-commentary
    \\ae # comment entire file and indent at the same time
