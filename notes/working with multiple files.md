# Vim Working with multiple files

[vim cheatsheet](http://www.worldtimzone.com/res/vi.html)


    # Open all files
    vim .
    
    # To open all files in a dir in tabs
    $ vim * -p
    
    # To open all files in a dir in horizontally splitted windows
    $ vim * -o
    
    # To open all files in a dir in vertically splitted windows
    $ vim * -O


### Tabs

    # Open files in tabs
    vim -p file1 file2 file3
    
    # Close a tab
    :tabc

    # close all tabs
    :qa

    # close all tabs with saving
    :wqa # or :tabo or :xa but don't use it :x

    # force to close all without saving
    :qa!

    # Edit a file in a new buffer
    :e filename 
    
    # go to next buffer
    :bnext (or :bn)
    
    # go to previous buffer
    :bprev (of :bp) 
    
    # delete a buffer (close a file)
    :bd
    
    # To open another tab
    :tabe file.rb
    
    # Move to the next tab
    gt # or gT or igt to go to i-th tab

    # close current tab
    :tabclose

    # close i-th tab
    :tabclose i

    # close all other tabs
    :tabonly

    # new window in the current tab, use <c-w>t to move this window to a new tab or :tab sp to be copied to a new tab
    :sp filename

    

### Windows

    # Open a file in a new buffer and split window
    :sp filename 
    
    # Vertically split window
    :vs filename
    
    # Quit a window
    <C-w>q 
    
    # Split windows vertically
    <C-w>v 
    
    # :new horizontal split (editing a new empty buffer)
    <C-w>n
    
    # :split window horizontally (editing current buffer)
    <C-w>s 
    
    # :vsplit window vertically (editing current buffer)
    <C-w>v 
    
    #  :close window
    <C-w>c
    
    # close all windows, leaving :only the current window open
    <C-w>o
    
    # go to next window
    <C-w>w
    
    # go to previous window
    <C-w>p
    
    # move around in windows
    <C-w>h # or use  h|j|k|l 
    
    # go to window above
    <C-w><Up> 
    
    # go to window below
    <C-w><Down>
    
    # go to window on left
    <C-w><Left>
    
    #  go to window on right
    <C-w><Right>
    
