# Vim plugins

## Using Vim-pathogen for vim-plugins
[Vim-pathogen](https://github.com/tpope/vim-pathogen)

Installing a plugin

    cd ~/.vim/bundle
    git clone git://github.com/username/plugin-name.git

Once you installed run the following to install help tags. This will generate documentation on every directory in 'runtimepath'.

    # you can check your runtimepath
    :set runtimepath?

    # Install doc
    :Helptags

If this doesn't work then add the following to your .vimrc

    set runtimepath^=~/.vim/bundle/newpluginname

Then run this in vim

    :helptags ~/.vim/bundle/newpluginname/doc


## ctrlp.vim

[ctrlp.vim](https://github.com/kien/ctrlp.vim)

Read this [installation guide](http://kien.github.io/ctrlp.vim/#installation)

This is similar to NERDTree but it opens multiple files at once and create new files and directories as well.

    # Using ctrlp
    ^p # ctrl + p and type 
    # to create a file
    crtl+p 
    ../newdir/newfile.md
    ctrl+y
    # more details check help
    :h ctrlp-input-format
    # and read f)




    
