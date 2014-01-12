# Neobundle, Vim plugin manager

I used [vim-pathogen](https://github.com/tpope/vim-pathogen) for a while and moved to  [neobundle.vim](https://github.com/Shougo/neobundle.vim). 

## Installation


    $ mkdir -p ~/.vim/bundle
    $ git clone git://github.com/Shougo/neobundle.vim ~/.vim/bundle/neobundle.vim
    # if you are using dotfiles
    $ git clone git://github.com/Shougo/neobundle.vim ~/dotfiles/.vim/bundle/neobundle.vim

I changed my .vimrc accordingly. [my latest .vimrc](https://github.com/shinokada/dotfiles/blob/master/.vimrc). 


    if has('vim_starting')
      set nocompatible               " Be iMproved
      set runtimepath+=~/.vim/bundle/neobundle.vim/
    endif
    
    call neobundle#rc(expand('~/.vim/bundle/'))
    
    " Let NeoBundle manage NeoBundle
    NeoBundleFetch 'Shougo/neobundle.vim'
    
    
    " My Bundles here:
    
    NeoBundle 'Shougo/neobundle.vim'
    NeoBundle 'scrooloose/nerdtree'
    NeoBundle 'tpope/vim-unimpaired'
    NeoBundle 'tpope/vim-fugitive' 
    NeoBundle 'gregsexton/gitv'
    NeoBundle 'SirVer/ultisnips'
    NeoBundle 'tyru/open-browser.vim'
    NeoBundle 'Trevoke/ultisnips-rspec'
    NeoBundle 'Shougo/vimshell'
    NeoBundle 'Shougo/unite.vim'
    NeoBundle 'itchyny/lightline.vim'
    NeoBundle 'suan/vim-instant-markdown'
    
     filetype plugin indent on     " Required!
     "
     " Brief help
     " :NeoBundleList          - list configured bundles
     " :NeoBundleInstall(!)    - install(update) bundles
     " :NeoBundleClean(!)      - confirm(or auto-approve) removal of unused bundles
    
     " Installation check.
     NeoBundleCheck
    
    " to turn syntax on
    syntax on
    
    " Use zsh for bash
    " set shell=/bin/zsh
    " for vim-instant-markdown
    set shell=bash\ -i 
    
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
    set autoindent
    
    " load indent file for the current filetype
    filetype indent on
    
    " to avoid removing indent when typing #
    :inoremap # X<BS>#
    
    " colorscheme
    " colorscheme darkblue
    
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
    
    " this auto-reload .vimrc when 
    augroup myvimrchooks
        au!
        autocmd bufwritepost .vimrc source ~/.vimrc
    augroup END
    
    " for printing to html
    " not printing number lines
    :let g:html_number_lines = 0
    
    " For spell checking 
    set spelllang=en_us
    
    " for itchyne/lightline
    if !has('gui_running')
      set t_Co=256
    endif
    set laststatus=2
    
    let g:Powerline_symbols = 'fancy'
    let g:lightline = {
          \ 'colorscheme': 'wombat',
          \ 'component': {
          \   'readonly': '%{&readonly?"":""}',
          \ },
          \ 'separator': { 'left': '', 'right': '' },
          \ 'subseparator': { 'left': '', 'right': '' }
          \ }


## Resources
[neobundle.vim](https://github.com/Shougo/neobundle.vim). 

[vim-users.jp](http://vim-users.jp/2011/10/hack238/)

[Read SHOUGO's blog](http://vinarian.blogspot.jp/)

[Read SHOUGO's slides](http://www.slideshare.net/Shougo/presentations)


