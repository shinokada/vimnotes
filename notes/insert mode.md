# Insert mode

## Making corrections from Insert Mode
This works in the bash shell as well.

    <C-h> # delete back one character
    <C-w> # Delete back one word
    <C-u> # Delete back to start of line

## Switching between Normal mode and Insert mode

    <Esc>
    <C-[> # to Normal mode
    <C-o> # to Insert Normal mode
    <C-c> # same as <Esc>
    gi # switches to insertion mode placeing the cursor at the same location it was previously. 
    g; # jump to the last place you made an edit
