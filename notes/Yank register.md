# Yank registered

## Yank

[Replace a word with yanked text](http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text)

[Vimの使い方](http://www15.ocn.ne.jp/~tusr/vim/vim_text1.html)


    yiw # yank inner word


## :reg " and :reg 0
When you use `x`, `s`, `d{motion}`, `c{motion}`, `y{motion}`, you are cutting to the default register.

    # To see what in the default register
    :reg "

    # To see what in the register 0, Yank register "0P
    :reg 0 # yank register


## Using reg 0 to paste

    # diw(delete inner word) will register in the default register.
    # In order to put the yanked word, use `"0P`.
    "0P

## True delete in vim, the black hole register "_

    # Just to delete, use "_{motion}. 
    # e.g. to delete a word
    "_diw

By using the balck hole register `"_`, you can delete a word and you P/p to paste rather than using a regitered yank.

    yiw
    jww
    "_diw
    P

[Meet the yank register](http://vimcasts.org/episodes/meet-the-yank-register/)

[Replace a word with yanked text](http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text)


## Within a file

    # copy to register a
    # <C-V> to change to visual mode and select line(s) or word(s) 
    "ay # use named reagisters ("a-"z)
    # to paste it
    "ap
    # cut to register b
    "bdd
    # to paste it
    "bp
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

## To copy from one file to another, the system clipboard`"+` and selection `"*` registers
For OSX and windows there is no primary clipboard, so `"+` and `"*` are the same system clipboard.

    # <C-v> to change to visual mode and select lines
    # to copy
    "+y
    # to paste
    "+p
    # paste from a external application
    "+p
    # for Insert mode
    <C-r>+

## Other registers

    `"=`

`<C-r>=` then you do calculation 1+1 and <CR> to insert the answer to the text.

    "% # name of the current file
    "# # name of the alternate file
    ". # Lst inserted text
    ": # last ex command
    "/ # last search pattern    

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
    
    

