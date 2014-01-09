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

## To paste text in inserting

    yt, # yank till ,
    jA # move down and Append a spece. Note a space after A
    <C-r>0 # to paste the text which yanked. Register 0 is for yanked.

You can use a regster to yank. `<C-r>{register}`.

`<C-r><C-p>{register}` inserts text and fixes any unintended indentation. See `:h i_CTRL-R_CRTL-p`. But it is better to use registers.



