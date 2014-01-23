# vimrc notes

## Example vimrc

[From vim.wikia.com](http://vim.wikia.com/wiki/Example_vimrc)

## My vimrc

```
scriptencoding utf-8
set encoding=utf-8

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
    NeoBundle 'Shougo/vimfiler.vim'
    NeoBundle 'itchyny/lightline.vim'
    NeoBundle 'suan/vim-instant-markdown'
    NeoBundle 'tpope/vim-commentary'
    NeoBundle 'beloglazov/vim-online-thesaurus'
    NeoBundle 'vim-scripts/TwitVim'
    NeoBundle 'xolox/vim-misc'
    NeoBundle 'xolox/vim-notes'
    NeoBundle 'szw/vim-dict'
    NeoBundle 'ervandew/supertab'
    NeoBundle 'tpope/vim-surround'


    NeoBundle 'Shougo/vimproc', {
          \ 'build' : {
                \     'mac' : 'make -f make_mac.mak',
                      \    },
                            \ }

                            filetype plugin indent on     " Required!

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

                            """"""""""""" for UltiSnips """"""""""""""
                            let g:UltiSnipsSnippetsDir ="/Users/teacher/.vim/bundle/ultisnips/UltiSnips"
                            let g:UltiSnipsEditSplit = "vertical"
                            let g:UltiSnipsListSnippets = "<c-j>"

                            """""""""" Set ultisnips triggers"""""""""""""
                            let g:UltiSnipsExpandTrigger="<tab>"                                            
                            let g:UltiSnipsJumpForwardTrigger="<tab>"                                       
                            let g:UltiSnipsJumpBackwardTrigger="<s-tab>"                                    

                            """""""""" NERDTree, Use F3 for toggle NERDTree """""""""""""""
                            nmap <silent> <F3> :NERDTreeToggle<CR>

                            " for backspace key to be used
                            set backspace=2

                            " For mouse click in NERDTree
                            set mouse=a
                            let g:NERDTreeMouseMode=3

                            """""""""""" For vim-instant-markdown """""""""""""""
                            let g:instant_markdown_slow = 1
                            let g:instant_markdown_autostart = 0

                            " Use esc to noh(nohighlight) the searched words
                            " nnoremap <esc> :noh<return><esc> " this creates a problem for down/up/right/left to insert A B C D

                            " Indentation
                            set autoindent

                            " load indent file for the current filetype
                            filetype indent on

                            " to avoid removing indent when typing #
                            inoremap # X<BS>#

                            """""""""" colorscheme """""""""""""
                            "set background=dark
                            "colorscheme solarized

                            """"""""" Adding cursor color """"""""
                            set cursorline
                            hi Comment ctermfg=103
                            hi CursorLine term=none cterm=none ctermbg=17 guibg=236

                            " Adding highlight for search
                            " set hlsearch

                            " set line numbers
                            set number

                            " word wrapping and inserted line breakes only when Enter key is hit
                            set wrap
                            set linebreak
                            set nolist  " list disables linebreak
                            set textwidth=0
                            set wrapmargin=0

                            " this auto-reload .vimrc when saved
                            augroup myvimrchooks
                                au!
                                    autocmd bufwritepost .vimrc source ~/.vimrc
                                    augroup END

                                    " for printing to html
                                    " not printing number lines
                                    let g:html_number_lines = 0

                                    """""""""" for itchyne/lightline"""""""""
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
                                                                    \ 'separator': { 'left': "\ue0b0", 'right': "\ue0b2" },
                                                                          \ 'subseparator': { 'left': "\ue0b1", 'right': "\ue0b3" }
                                                                                \ }


                                                                                " treat all numerals as decimal not octal 
                                                                                set nrformats=

                                                                                """""""""""" Thesaurus dir"""""""""""""
                                                                                "set thesaurus+=~/.vim/thesaur/mthesaur.txt
                                                                                set thesaurus+=~/.vim/thesaur/ruby-functions.txt

                                                                                " mapping English spelling functionality 
                                                                                map <F5> :setlocal spell! spelllang=en_us<CR>
                                                                                imap <F5> <C-\><C-o>:setlocal spell! spelllang=en_us<CR>

                                                                                """""""""""TwitVim"""""""""""""""""""""
                                                                                nnoremap ,tp :<C-u>PosttoTwitter<CR>
                                                                                nnoremap ,tf :<C-u>FriendsTwitter<CR><C-w>j
                                                                                nnoremap ,tu :<C-u>UserTwitter<CR><C-w>j
                                                                                nnoremap ,tr :<C-u>RepliesTwitter<CR><C-w>j
                                                                                nnoremap ,tn :<C-u>NextTwitter<CR>
                                                                                autocmd FileType twitvim call s:twitvim_my_settings()
                                                                                function! s:twitvim_my_settings()
                                                                                  set nowrap
                                                                                  endfunction

                                                                                  """"""""""TwitVim"""""""""""""""""""""""""
                                                                                  let twitvim_count = 50
                                                                                  let twitvim_browser_cmd="open"

                                                                                  """"""""" Supertab"""""""""""""""""""""""""
                                                                                  " use tab for autocomplete
                                                                                  let g:SuperTabDefaultCompletionType = "<C-X><C-O>"
                                                                                  " lets SuperTab decide which completion mode to use 
                                                                                  let g:SuperTabDefaultCompletionType = "<c-n>"

                                                                                  """"""""" Eliminating delays on ESC in vim """""""""""""
                                                                                  set timeoutlen=1000 ttimeoutlen=0

                                                                                  """"""" unite.vim """""""""
                                                                                  nnoremap <C-p> :Unite file_rec/async<cr>


                                                                                  """" lightline.vim
                                                                                  set guifont=Inconsolata\ for\ Powerline:h15

```                                      
