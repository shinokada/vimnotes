# Vim notes

## Vim Resources

[VIM QUICK REFERENCE CARD](http://tnerual.eriogerg.free.fr/vimqrc.html)


## Vim Tutorial

    vimtutor

[Learnvim](https://github.com/dahu/LearnVim)

    :h learnvim
    

## Reload .vimrc

    :so %

### To repeat the last change.

    . (dot) 

### Undo

    :edit! # get into the earliest saved state.
    
### Indent

    # indent a line 

    >> 

    # Indent three lines.

    >>j.j. or >3> or 3>>

    # Indent from the current line to the end of the file
    >G


### Delete

    # Change
    c

    # Change word/Word to abc
    cwabc # cWabc

    # To delete the character under the cursor.
    x 

    # Delete three characters
    x... # or 3x

    # To delete the current line
    dd 

    # Delete two lines
    dd.  # or d2d or 2dd

    # Delete upto the end of line and ready to type.
    C # or c$, c stands for change

    # Delete one letter and enters Insert mode.
    s # or cl

    # Delete the line and enters Insert mode.
    S # or ^C

    # Delete a word
    daw

    # Delete backward
    db

    # Delete forward
    dw

    # Delete up to the second comma
    d2t,


### Move around
[vim vikia: Moving around](http://vim.wikia.com/wiki/Moving_around)
[All the right move](http://vim.wikia.com/wiki/All_the_right_moves)


    # move to the beginning of the line
    0

    # move to the end of the line
    $

    # move to the first non-blank
    ^

    # go to the last non-blank character of line
    g_

    # word, end and back
    w # W
    e # E
    b # B
    
    # Jump forward/backward one sentence.
    ) # (

    # Jump forward/backward one paragraph
    } # {

    # Move to the beginning of the line and chnage to the insert mode.
    I or ^i

    # Move to the end of line and enters Insert mode.
    A # or $a

    # move backward by word
    b

    # move forward by word
    w

    # move to the beginning of the line
    0

    # find, find backward
    f # F

    # find till, find till backward
    t # T


### Move and insert 

    # Replace mode, enter insert mode with typing over existing characters
    R

    # Append, move to the end of line and insert mode
    A

    # Open below. Insert a new line under the current line and enters Insert mode.

    o # or A<CR>

    # Open above. Insert a new line above the current line and enters Insert mode.

    O # or ko

    # Undo,  redo and undo all in the line
    u
    ^R
    U

### To end vim

    ZZ, :x, :wq # write and quit
    :q! # without write and quit
    :e! # return to the original


### Saving files

    :w! # to overwrite
    :w filename # to save to a newfile

### Help

    :h # or :help
    ZZ # to end help
    # on a tag 
    ^] # will move to that tag
    # going back
    ^t
    #  get the help on yank
    :h yank
    # get the help on ^A
    :h ^a
    # get the help on ^h with the insert mode
    :h i_^h

### Change

    # find +
    f+
    # s deletes the character and then enters insert mode
    # enter changes space + space
    s + 
    # repeat the last search
    ;
    # repat
    .
    # repeat search and replace
    ;.
    
    # Change till ?
    ct? # or ct<letter>
    
    # Change and find ?
    cf? # or cf<letter>



### Search 

    # scan line for next character 
    fx
    # scan line for previous charcter
    Fx
    # scan line for next character and move to the left of the letter x
    tx
    # scan line for previous character and move to the right of the letter x
    Tx
    # scan document for next match
    /pattern<CR>
    # scan document for previous match
    ?pattern<CR>
    # will search for the word under the cursor
    * 
    # clear word(cw)(and change to insert mode) and type new word
    cwnewword<ESC>
    # next search
    n
    # repeat the change
    .

### Repeat and reverse

    # repeat fx, Fx, tx, Tx
    ;
    # reverse fx, Fx, tx, Tx
    ,
    # repeat /pattern or ?pattern
    n
    # reverse /pattern or ?pattern
    N

### Substitue

[Search and replace](http://vim.wikia.com/wiki/Search_and_replace)

    s[ubstitute]
    :s/target/replacement
    # repeat substitue
    &
    # reverse it
    u
    # g-flag for global
    :s/foo/bar/g    # Change each 'foo' to 'bar' in the current line.
    :%s/foo/bar/g    # Change each 'foo' to 'bar' in all lines.

### Spell checking

    :set spell spelllang=en_us
    # set locally
    :setlocal spell spelllang=en_us
    # turn off spelling
    :set nospell
    # find next misspelled word
    ]s
    # find previous misspelled word
    [s
    # find alternatives
    z= # and type number

### Adding and subtracting

    # add 1 to a number at or after the cursor. This will look ahead for a digit and jumps to it.
    <C-a> # ctrl+a
    # subtract 1 from a number
    <C-x>
    # add 10 to a number
    10<C-a>
    # subtract 180
    180<C-x>

## Vim tabs

    # opening vim with multiple files
    vim -p file1 file2
    # toggle between files
    gt # gT

## Adding comment outs

    <C-v> # select lines
    I#<Esc>


## Yank and paste

    # yank all lines
    :%y+
    # paste
    p


## Using terminal in vim

    Hit <kbd>ctrl-z</kbd> to go to terminal. Type <kbd>fg</kbd> to go back to vim.


## Deleting the first 2 spaces for multiple lines

# Remove the first 2 characters of every line:

    :%normal 2x
    

# Remove first 2 characters of every line, only if they're spaces:

    :%s/^  # Note: there are two spaces after ^. 
    
    # Move indentation to left for every line:
    
    :%normal <<


## Yank

[Replace a word with yanked text](http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text)

[Vimの使い方](http://www15.ocn.ne.jp/~tusr/vim/vim_text1.html)


    yiw # yank inner word

## Vim’s terminology

Vim vs Normal
put = paste
yank = copy
delete(and kepp it in a register) = cut


## Visual mode

[Vim 101 visual mode](http://usevim.com/2012/05/11/visual)

[vimdoc visual](http://vimdoc.sourceforge.net/htmldoc/visual.html)

    v # per character
    V # linewise
    <C-v) # blockwise
    
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
    
    # operators help
    :h visual-operators



## Increasing and Decreasing numbers

    # to increase one
    <C-a>
    # to decrease one
    <C-x>


