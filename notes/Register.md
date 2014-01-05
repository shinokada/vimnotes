# Register

## Visual selection

    yiw
    jww
    ve # select with visual mode upto the end of the word
    p # this will replace the selected part with the yanked word.

    # highlight the previously selected part.
    gv

Note that in visual mode, `p` gets the contents of the unnamed register and it sets the contents of the unnamed register. 

`m{char}` sets a mark and ``{char}` jumps to the mark.

    fc # find the first character c
    de # delete that word till end
    mm # mark the position as m
    
`gp` and `gP` is useful for `p` and `P`. `gP` will paste and put the cursor at the end.



