# Vim tips

## Using backspace/delete

Add this to your .vimrc

    :set backspace=2

## Using mouse in vim

    # in your .vimrc
    :set mouse=a
    # for NERDTree
    let g:NERDTreeMouseMode=3 

## Display current working file path and name

    :echo expand('%:p')

## Replacing 

    # replace " at the beginning of each lines with four spaces. Note a space after ".
    :%s/^ /    / # note that you don't need the last / but there are four spaces.
    # move intentation to left for every line
    :%normal <<


## Select all and yank

    gg"+yG

    :%y+

## Reload .vimrc from Vim

    # if you are in .vimrc
    :so %
    # from other file
    :so $MYVIMRC

    # check your .vimrc
    :echo $MYVIMRC

Or add the following to your .vimrc to auto-load

ex1

    augroup myvimrchooks
        au!
        autocmd bufwritepost .vimrc source ~/.vimrc
    augroup END

ex2 [Auto-Reload Your Vimrc](http://www.bestofvim.com/tip/auto-reload-your-vimrc/)

    augroup reload_vimrc " {
        autocmd!
        autocmd BufWritePost $MYVIMRC source $MYVIMRC
    augroup END " }


## No highlight after search
After a search words are hightlighted. but using `:noh` or `:nohl` hightlight will be disabled. If you want it back then type `n`.

    :noh

## vim and shell

    # go to shell
    :sh 
    :shell
    # go back to vim
    exit

    # go to shell
    ctrl+z
    # go back to vim

## Save as

    :w ~/dirname/filename.md
    # to overwrite
    :w! ~/dirname/filename.md

## Printing vim doc

Print it out from a browser. 

    # change to html
    :TOhtml
    # save it
    :w ~/Documents/filename.html
    # open it in a browser and print it out
    # or save it as a txt and open it from another programme and print it out.
    
## Delete all

    :%d

% is all lines in range. So you can use `:%s/old/new/g` to substitute all.

## Range 
[Range](http://vim.wikia.com/wiki/Ranges)

    1 # first line
    $ # last line
    . # current line
    % # all lines
    21,25 # lines 21 to 25 inclusive
    .,$ # current line to end

