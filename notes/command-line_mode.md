# Command-line mode

    # delete backword
    <C-w>
    # delete backword to the start of the line
    <C-u>
    # paster from a register
    <C-r>{register}

## Execute a command on one or more consecutive lines
Tip 28

    # move to line 3 and delete the line
    :3d # same as 3Gdd
    # delete line from 2 to 5
    :2,5d
    # delete line from 2 to the end
    :2,$d
    # delete all lines in the file
    :%d # same as 1,$d

### Substitue a word within a range of lines selected by visual selection

`'<` is start of visual selection and `'>` is end of visual selection.

    # Move to line 10 and select from there to the end
    10GVG
    # when you type :, it will display :'<,'>
    # substitue this with that
    :'<,'>s/this/that
    # substitute all this with that in all lines
    :%s/this/that

### Specify a range of lines by patterns

Range `:{start},{end}`. For pattern `:/pattern/,/patter/d`.

General form for an offset, `:{address}+n` and default `n` is 1 so you can ommit it.

    :/<html>/,/<\/html>/d
    # select <html></html> block except <html> and </html> and delete
    :/<html>/+1,/<\/html>/-1/d
    # . means current line
    # select from the current line and 3 more lines, total 4 lines, and delete
    :.,.+3d

## Duplicate lines `:t`
Tip 29

`.` stands for the current line. Use `:[range]copy{address}` to copy range and paste it to address.

    # Make a copy of line 6 and put it below the current line
    :6copy. # or :6co.
    # shorthand is :t for copy
    :6t.
    # copy the current line to just below line 6
    :t6
    # duplicate the current line, same as yyp
    :t.
    # copy the current line to the end of the file
    :t$
    # copy the visually selected lines to the start of the file
    # 0 is the virtual line above first line of the file
    # after visual selection, when you type :, '<,'> will appear
    :'<,'>t0

`yyp` uses a register whereas `:t` doesn't. `:6t.` in command line is the same as `6Gyy<C-o>p` in normal mode.
`<C-o>` jump to older cursor position.

## Move lines with :m

The :move command is used in `:[range]move {address}` or use shorthand `:[range]m{address}`

    # select lines
    Vjj
    # move to the end of file
    :'<,'>m$
    # this is the same as to delete the selection, move to the end and paste in normal mode
    dGp
    # to repeat the last Ex command 
    @:

## Run normal mode commands across a range
Tip 30

Use `:normal` to run normal-mode commands, such as `.` etc.

    # Apend ;
    A;<Esc>
    # go one line down and change to a visual-mode and select to the end of the file
    jVG
    # change to a normal-mode and repeat
    # for each line in the visual selection, execute the normal mode . command
    :normal.
    # This can be done
    :%normal A;
    # or use a range
    :2,9normal A;

Vim moves the cursor to the beginning of the line with :normal so you don't need to worry about where the cursor is about

    :%normal i//

## Repeat the last ex command
Tip 31

Use `@:` to repeat the last ex command.

    # list a command which is in the buffer
    :bn[ext]
    # backward 
    :bp[previous]
    # then repeat it
    @:
    # and repeat it again
    @@

## Tab to complete ex commands
Tip 32 

    # <C-d> to reveal a list of possible completions. 
    # use <Tab> or <S-Tab> to cycle through
    :col<C-d>    
    :colorscheme <C-d>

With the 'wildmenu' option enabled, Vim provides a navigable list of suggestions.
Use `<Tab>`,`<S-Tab>`, `<C-n>`, `<C-p>` or `<Right>`, `<Left>`

    set wildmenu
    set wildmode=full

## Insert the current word at the command prompt
Tip 33

<C-r><C-w> gets the word under the cursor. Use it with help to look up the documentation `:h <C-r><C-w>`

`*` command searchs for each orrurrence under cursor.

    # select a word under cursor 'tally'
    *
    # change the word to "counter" and escape
    cwcounter<Esc>
    # use substitute to change all 'tally' to 'counter'
    :%s//<C-r><C-w>/g

## Recall commands from history

`:` and <Up>,<Down> key show the command history.

`:h` and <Up>,<Down> key show the help history.

`/` and <Up>,<Down> key show the search histroy.

Vim records the last 20 commands. You can change `history` number.

    set history=200



