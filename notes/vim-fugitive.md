# vim-fugitive

[vim-fugitive](https://github.com/tpope/vim-fugitive)
[vimcast](http://vimcasts.org/episodes/fugitive-vim---a-complement-to-command-line-git/)

## When to use it

git commands which generate little or no output.

git log is better in the shell. :Git checkout -b experimental is good to use vim-fugitive.

## Git and fugitive commands
    :help cmdline-special
    :help :Gread

| git                  | fugitive       | action                                                      |
|----------------------|----------------|-------------------------------------------------------------|
|:Git add %            |:Gwrite         |Stage the current file to the index                          |
|:Git checkout %       |:Gread          |Revert current file to last checked in version               |
|:Git rm %             |:Gremove        |Delete the current file and th corresponding Vim buffer      |
|:Git mv % target_path |:Gmove          |Rename the current file and the corresponding Vim buffer     |


## Gremove and Gmove

:Gremove does a git rm on a file and simultaneously deletes the buffer.

    :Git rm % 
    :bwipeout # need to clean up buffer

:Gmove does a git mv on a file and simultaneously renames the buffer.

    git mv original/path destination/path
    :bwipeout original/path
    :edit destination/path

`:Gmove target_path`, destination is relative to the path of the current file.

`:Gmove /target_path` destination is relative to the root of the git repository.

## Gcommit

After `Gcommit`, enter commit message without `"`.

For Autocomplete use `Ctrl-n`.


## Alias in .gitconfig works with :Git 

    # from my .gitconfig
    [alias]
    co = checkout
    ci = commit
    st = status
    br = branch
    hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
    type = cat-file -t
    dump = cat-file -p
    df = diff
    dc = diff --cached
    lg = log -p
    who = shortlog -s --

You can use tab completion. If you have a branch called experimental, you can complete with tab.

    :Git co -b exper<tab>



