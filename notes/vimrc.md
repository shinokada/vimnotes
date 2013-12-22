# vimrc notes

## Example vimrc

[From vim.wikia.com](http://vim.wikia.com/wiki/Example_vimrc)

## My vimrc

```
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
NeoBundle 'shinokada/autoswap_mac'
NeoBundle 'shinokada/listtrans.vim'
NeoBundle 'shinokada/SWTC.vim'
NeoBundle 'shinokada/dragvisuals.vim'

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

" this auto-reload .vimrc when saved
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

"==========[ Damian Conway OSCON 2013: More Instantly Better Vim"]============

"====[ Make the 81st column stand out ]====================

    " just the 81st column of wide lines...
    highlight ColorColumn ctermbg=magenta
    call matchadd('ColorColumn', '\%81v', 100)


"====[ Make tabs, trailing whitespace, and non-breaking spaces visible ]======

    exec "set listchars=tab:\uBB\uBB,trail:\uB7,nbsp:~"
    set list


"====[ Swap : and ; to make colon commands easier to type ]======

"    nnoremap  ;  :
"    nnoremap  :  ;


"====[ Always turn on syntax highlighting for diffs ]=========================

    " EITHER select by the file-suffix directly...
    augroup PatchDiffHighlight
        autocmd!
        autocmd BufEnter  *.patch,*.rej,*.diff   syntax enable
    augroup END



"====[ autoswap_mac.vim ]============

set title titlestring=

"====[ listtrans.vim ]==========

nmap  ;l   :call ListTrans_toggle_format()<CR>
vmap  ;l   :call ListTrans_toggle_format('visual')<CR>

"====[ dragvisulas.vim ]=========

runtime plugin/dragvisuals.vim

vmap  <expr>  h        DVB_Drag('left')
vmap  <expr>  l        DVB_Drag('right')
vmap  <expr>  j        DVB_Drag('down')
vmap  <expr>  k        DVB_Drag('up')

" Remove any introduced trailing whitespace after moving... 
let g:DVB_TrimWS = 1
```
