# Vim grep

## Resources
[Vim.wikia](http://vim.wikia.com/wiki/Find_in_files_within_Vim)
[Vim+Grep](http://lostechies.com/derickbailey/2010/05/11/vim-grep-find-all-occurrences-of-text-in-your-project/)
[Using Grep from Inside Vim](http://java.dzone.com/articles/using-grep-inside-vim)

## Basics

    # check your pwd
    :pwd
    # Search within the project folder 
    :vimgrep /pattern/gj ./**/*.php
    # display it
    :cw

`g` flag will return all matches. With `j` flag, Vim won't jump to the first match. 

    :cn # to jump to the next match.



## From Vim+Grep
Using macro.

    :qccwcommand<Esc>:w<Ctl-W>jj<Enter>q

This macro will change the current ‘path_to_command’ word to ‘command’, write the file out to disk, change window splits to the grep search results, move down one line in the results and navigate to that result’s location. I ran the macro by hitting @c and then verifying the line selected was one that I wanted to change. For a few instances where I did not want to change the line, I manually navigated to the next search result and then re-ran the @c macro.

