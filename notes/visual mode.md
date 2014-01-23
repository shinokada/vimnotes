# Visual mode


## Visual mode

[Vim 101 visual mode](http://usevim.com/2012/05/11/visual)

[vimdoc visual](http://vimdoc.sourceforge.net/htmldoc/visual.html)

Practical vim Tip #21

    v # per character, this v is actually toggling normal and character-wise visual mode
    V # linewise, Switch to Normal mode
    <C-v) # blockwise
    gv # reselect the last visual selection

    # select4 lines above
    4k
    
    # select 3 lines below
    3j
    
    # select 2 words
    2w
 
    # go back to the previous visual mode
    gv
    
    # go back to the other end
    o # or O
    vbb # Start from the beginning of a word, change to character-wise visual mode, go back two words, the cursor is on the far left
    o # to move the cursor to the other end
    e # to select upto the end of the word
    
    # operators help
    :h visual-operators

## Using a visual operator
Tip 23

    # vit means visually select inside the tag
    # This will highlight one in <a href="#">one</a>
    vit
    # convert the selected characters to uppercase
    U
    # down and repeat
    j.

The above will work for the same number of letters. If a word is longer than the first one, it will convert partially.

    # Normal mode equivalent of U is gU{motion}, h:gU
    gUit
    j.
    j.

This will change any length of words.

## Example of visual block mode

    # change to visual block and select 3 lines 
    <C-v>3j
    # delete a character and repeate it
    x...
    # reselect 
    gv
    # replace the selected by pipes
    r|
    # yank a line and paste it
    yyp
    # select a line and replace all characters with -
    Vr-




















