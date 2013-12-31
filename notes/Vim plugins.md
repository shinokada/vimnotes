# Vim plugins


## Supertab
[maketecheasier](http://www.maketecheasier.com/8-vim-plugins-to-enhance-your-productivity/)

[Github repo](https://github.com/ervandew/supertab)

[Using Supertab](http://vim.wikia.com/wiki/Omni_completion_popup_menu)


The SuperTab plugin can be used to avoid needing to press Ctrl-X then Ctrl-O to invoke the popup completion menu. With SuperTab installed, the following setting means you can just press Tab instead.

    let g:SuperTabDefaultCompletionType = "<C-X><C-O>"

You may also try the context value, which lets SuperTab decide which completion mode to use and should play well with OmniCompletion:

    let g:SuperTabDefaultCompletionType = "context"

## Surround
[Github repo](https://github.com/tpope/vim-surround)

Press `cs"'` inside

    "Hello world!"

to change it to

    'Hello world!'

Now press `cs'<q>` to change it to

    <q>Hello world!</q>

To go full circle, press `cst"` to get

    "Hello world!"

To remove the delimiters entirely, press `ds"`.

    Hello world!

Now with the cursor on "Hello", press `ysiw]` (`iw` is a text object).

    [Hello] world!

Let's make that braces and add some space (use `}` instead of `{` for no
space): `cs]{`

    { Hello } world!

Now wrap the entire line in parentheses with `yssb` or `yss)`.

    ({ Hello } world!)

Revert to the original text: `ds{ds)`

    Hello world!

Emphasize hello: `ysiw<em>`

    <em>Hello</em> world!

Finally, let's try out visual mode. Press a capital V (for linewise
visual mode) followed by `S<p class="important">`.

    <p class="important">
      <em>Hello</em> world!
    </p>

This plugin is very powerful for HTML and XML editing, a niche which
currently seems underfilled in Vim land.  (As opposed to HTML/XML
*inserting*, for which many plugins are available).  Adding, changing,
and removing pairs of tags simultaneously is a breeze.

The `.` command will work with `ds`, `cs`, and `yss` if you install
[repeat.vim](https://github.com/tpope/vim-repeat).


## Vim-dict
[Github repo](https://github.com/szw/vim-dict)


Usage
-----

To lookup a word (or words) in the dictionary use `Dict` command:

    :Dict hello
    :Dict start up

The `Dict` command uses hosts and databases defined in the `g:dict_hosts` global list. By default it is set to
`[["dict.org", ["all"]]]` (the format will be explained a bit later).

`Dict` command can use a word under the cursor. Just move the cursor to a word and type in the command line:

    :Dict

The same works on selection - just select multiple words in the Visual mode.

The `:Dict` command will open a preview window. To close that window you may run `:pc`, or just hit
`q` if the Dict window is the active one.


Configuration
-------------

There are just a few global variables (options) you may set in the *.vimrc* file.

* `g:dict_hosts`

  The most important one is a list `g:dict_hosts` mentioned earlier. It combines hosts/databases used by
  **vim-dict**. The list entries are lists themselves and share the following format:

        ["host_name", ["database1", "database2", ...]]

  The sample extract from someone's  *~/.vimrc* file could look like this:

        let g:dict_hosts = [
            \["dict.org", ["all"]],
            \["dict.mova.org", ["slovnyk_en-pl", "slovnyk_pl-en"]]
        \]

  Moreover **vim-dict** can help you figure out what databases are available on your servers. There is
  a special command for this:

        :DictShowDb

  You can even open your *.vimrc* and provide some host urls only:

        let g:dict_hosts = [
            \["dict.org", []],
            \["dict.mova.org", []]
        \]

  Then save and reload *.vimrc*, perform `DictShowDb` and yank-paste the databases you want :).

  The list of DICT servers can be found on the Internet, e.g.
  [here](http://luetzschena-stahmeln.de/dictd/index.php).



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


    
##<del> Using Vim-pathogen for vim-plugins</del>

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
