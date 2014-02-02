# Buffer list and argument list

[Vim buffer FQA](http://vim.wikia.com/wiki/Vim_buffer_FAQ)

[Argument list](http://vimdoc.sourceforge.net/htmldoc/editing.html#argument-list)

## Argument list
[Meet the arglist](http://vimcasts.org/episodes/meet-the-arglist/)

If you give more than one file name when starting Vim, this list is remembered
as the argument list.  You can jump to each file in this list.
You can think of the arglist as being a stable subset of the buffer list. The contents of the buffer list can change often, and sometimes without you realizing it. Whereas the arglist will only change its contents when you give an explicit instruction for it to do so.

    # open more than one file.
    $ vim a.txt b.txt
    # args list. Active buffer with square brackets [a.txt] b.txt
    :args
    # close all files without warning
    :qall

## Traversing the arglist

    Ex command     | unimpaired map    | effect
    ---------------|-------------------|-----------
    :prev[ious]    | [a                |  reverse through argument list
    :next          | ]a                |  advance through argument list
    :first         | [A                |  go to start of arglist
    :last          | ]A                |  go to end of arglist

## Working with buffers
[Working with buffers](http://vimcasts.org/episodes/working-with-buffers/)

[Read my notes](../buffer.md). 

    # open buffer list
    :ls # or :buffers
    # open a new buffer but does not affect the argument list
    :e filename
    # next buffer
    :bn
    # previous buffer
    :bp

