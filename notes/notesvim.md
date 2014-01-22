# vim-notes
[xolox/vim-notes](https://github.com/xolox/vim-notes)

[notes.vim](http://peterodding.com/code/vim/notes/)

## Starting notes

    :Note 
    # from vim commands
    :edit note: # :tabedit note:, :split note:
    :edit note:title # :tabedit note:title, :split note:title
    # select a text and
    \en # :NoteFromSelectedText

## Saving

    :w # :write, :update, no file name. It will use the title. 

## Note directory

All notes are saved in .vim/bundle/vim-notes/misc/notes/user/ directory

## Edit

    :Note filetitle # use tab completion

## Delete

    :DeleteNote # to delete current file


## Searching

   :SearchNotes keyword … # searches for keywords 
   :SearchNotes /pattern/ #  searches for regular expressions

The `:SearchNotes` command supports tab completion of keywords and sorts candidates by relevance ([Levenshtein distance] [levenshtein])

## Smart defaults
Without an argument `:SearchNotes` searches for the word under the cursor (if the word starts with `@` that character will be included in the search, this means you can easily search for *@tagged* notes)

## Back-references
The `:RelatedNotes` command find all notes referencing the current file

## List by date
The `:RecentNotes` command lists your notes by modification date, starting with the most recently edited note
 
## Navigating between notes
The included syntax script highlights note names as hyper links and the file type plug-in redefines [gf] [gf] to jump between notes (the [Control-w f] [ctrlwf] mapping to jump to a note in a split window and the [Control-w gf] [ctrlwgf] mapping to jump to a note in a new tab page also work)

## Writing aids
The included file type plug-in contains mappings for automatic curly quotes, arrows and list bullets and supports completion of note titles using Control-X Control-U and completion of tags using Control-X Control-O

## Embedded file types 
The included syntax script supports embedded highlighting using blocks marked with `{{{type … }}}` which allows you to embed highlighted code and configuration snippets in your notes
