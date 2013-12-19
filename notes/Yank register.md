# Yank registered

## :reg " and :reg 0
When you use x, you are cutting to the default register.

    # To see what in the default register
    :reg "

    # To see what in the register 0
    :reg 0 # yank register


## Using reg 0 to paste

    # diw(delete inner word) will register in the default register.
    # In order to put the yanked word, use `"0P`.
    "0P

## True delete in vim

    # Just to delete, use "_. 
    # e.g. to delete a word
    "_diw

[Meet the yank register](http://vimcasts.org/episodes/meet-the-yank-register/)

[Replace a word with yanked text](http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text)


## Within a file

    # copy to register a
    # <C-V> to change to visual mode and select line(s) or word(s) 
    "ay # use a-z
    # to paste it
    "ap
    # check it in register
    :reg "a:
    # Delete it in the register a
    qaq
    # check it again
    :reg "a # should be nothing in register a
    # help 
    :h quote_alpha
    # You can append to a register
    "Ayy # to append to a line
    # or use
    :yank A 
    # or append all lines which has def
    :global/def/yank A

[Using Vim's named registers](http://vimcasts.org/episodes/using-vims-named-registers/)

## To copy from one file to another

    # <C-v> to change to visual mode and select lines
    # to copy
    "+y
    # to paste
    "+p

## To swap two arguments

    execute(second, first)
    fs # find s to move to second
    yiw # yank inner word. This will yank to the default register "" and "0
    w # to move one word forward, first
    viw # to visual inner word to select first
    p # to overwrite it with second. And 'first' will be registed in "" 
    :reg "0 # to check it
    # # hash key # to search backward under the cursor. This will move back to the first argument.
    viw # visual inner word
    p # to paste
    
    

