# Spelling and autocompletion

## vim-online-thesaurus
[vim-online-thesaurus](https://github.com/beloglazov/vim-online-thesaurus)

    <Local leader>K # \K
    q # to quit

## File Name Autocompletion

    # insert mode
    <c-x><c-f>

    # normal mode
    :e <tab>

## Autocompletion general File

[Geek Stuff](http://www.thegeekstuff.com/2009/01/vi-and-vim-editor-5-awesome-examples-for-automatic-word-completion-using-ctrl-x-magic/#more-328)

    <c-x><c-n> # word completion from the existing words in the current file
    <c-x><c-l> # line completion
    <c-x><c-f> # file name completion
    <c-x><c-k> # dictionary word completion. Need to set dictionary+=/usr/share/dict/words in .vimrc

[Geek Stuff: Vim Thesaurus](http://www.thegeekstuff.com/2008/12/vi-and-vim-editor-3-steps-to-enable-thesaurus-option/)

    <c-x><c-t> # to display thesaurus

[usevim](http://usevim.com/2012/07/06/vim101-completion/)


## Spell check

[Using spell checking in Vim](https://www.linux.com/learn/tutorials/357267-using-spell-checking-in-vim)

    :set spell spelllang=en_us
    :set nospell
    # move to a missspelled word
    ]s # or [s
    # get a list of suggestion
    z=
    # add to your dictionary
    zg

