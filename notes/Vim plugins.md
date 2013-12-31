# Vim plugins

## Using Vim-pathogen for vim-plugins

**I am using Neobundle now.**

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

## Supertab
[maketecheasier](http://www.maketecheasier.com/8-vim-plugins-to-enhance-your-productivity/)

[Github repo](https://github.com/ervandew/supertab)

## Surround
[Github repo](https://github.com/tpope/vim-surround)

## Vim-dict
[Github repo](https://github.com/szw/vim-dict)

## notes.vim
[peterodding](http://peterodding.com/code/vim/notes/)

[Github repo](https://github.com/xolox/vim-notes)

## TwitVim
[Githup repo](https://github.com/vim-scripts/TwitVim)

Use TinyURL for URL shortner.

The following are added to .vimrc.

    """ twitvim
    nnoremap ,tp :PosttoTwitter<CR>
    nnoremap ,tf :FriendsTwitter<CR>
    nnoremap ,tu :UserTwitter<CR>
    nnoremap ,tr :RepliesTwitter<CR>
    nnoremap ,tn :NextTwitter<CR>
    autocmd FileType twitvim call s:twitvim_my_settings()
    function! s:twitvim_my_settings()
      set nowrap
    endfunction

    " twitvim
    let twitvim_count = 50


    
