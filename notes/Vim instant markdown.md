# Vim instant markdown + Mavericks + zsh

[vim-instant-markdown](https://github.com/suan/vim-instant-markdown)

## Installation
You need to follow the github repo installation. 

    gem install pygements.rb
    gem install redcarpet
    npm -g install instant-markdown-d

Download the repo and move to `after/ftplugin/markdown/instant-markdown.vim` to
`~/.vim/after/ftplugin/markdown/`. Since I am using [vim-pathogen](https://github.com/tpope/vim-pathogen)
I move to `~/.vim/bundle/after/ftplugin/markdown/`. 

Then open .vimrc and add the followings.

    filetype plugin on
    # you need this for zsh   
    set shell=bash\ -i

Then you need to open md file with vim and it will open a browser http://localhost:8090/.

More info read [the doc](https://github.com/suan/vim-instant-markdown)
