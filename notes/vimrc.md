# vimrc notes

## Example vimrc

[From vim.wikia.com](http://vim.wikia.com/wiki/Example_vimrc)

## My vimrc

    set nocompatible " Turn off vi compatibility

    " for pathogen
    execute pathogen#infect()
    
    " for pathogen to turn syntax on
    syntax on

    " for pathogen, filetype plugin indent on
    filetype plugin on

    " Use zsh for bash
    set shell=/bin/zsh

    " tab setting
    set noeb vb t_vb=
    set expandtab
    set shiftwidth=2
    set softtabstop=2

    " for UltiSnips
    let g:UltiSnipsSnippetsDir ="/Users/teacher/.vim/bundle/ultisnips-master/UltiSnips"
    let g:UltiSnipsEditSplit = "vertical" 
    let g:UltiSnipsListSnippets = "<C-tab>"

    " NERDTree, Use F3 for toggle NERDTree
    nmap <silent> <F3> :NERDTreeToggle<CR>

    " for backspace key to be used
    :set backspace=2

    " For mouse click in NERDTree
    :set mouse=a
    let g:NERDTreeMouseMode=3 

    " Use esc to noh(nohighlight) the searched words
    " nnoremap <esc> :noh<return><esc> " this creates a problem for down/up/right/left to insert A B C D

    " Indentation
    set smartindent
    set autoindent

    " load indent file for the current filetype
    filetype indent on

    " to avoid removing indent when typing #
    :inoremap # X<BS>#

    " colorscheme
    colorscheme darkblue

    " Adding cursor color 
    set cursorline
    hi Comment ctermfg=103
    hi CursorLine term=none cterm=none ctermbg=17 guibg=236

    " Adding highlight for search
    set hlsearch

    " set line numbers
    set number

    " word wrapping and inserted line breakes only when Enter key is hit
    set wrap
    set linebreak
    set nolist  " list disables linebreak
    set textwidth=0
    set wrapmargin=0

    " status settings
    set cmdheight=1
    set laststatus=2
    set statusline=%<%F\ %m%r%h%w%{'['.(&fenc!=''?&fenc:&enc).']['.&ff.']'}%=%l,\ [TYPE=%Y]\ [ASCII=\%03.3b]\ [HEX=\%02.2B]\ %c%V%8P

    " ctrlp.vim 
    set runtimepath^=~/.vim/bundle/ctrlp.vim
