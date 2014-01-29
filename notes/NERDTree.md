# Vim plugin NERDTree

## NERDTree doc

[NERDTree doc](https://github.com/scrooloose/nerdtree/blob/master/doc/NERD_tree.txt)

## Adding a file

    # bring up NERDTree filesystem menu
    m
    # add child node
    a

## Quick help 

    NERD tree (4.2.0) quickhelp~
    ============================
    File node mappings~
    single-click,
    <CR>,
    o: open in prev window
    go: preview
    t: open in new tab
    T: open in new tab silently
    middle-click,
    i: open split
    gi: preview split
    s: open vsplit
    gs: preview vsplit

    ----------------------------
    Directory node mappings~
    single-click,
    o: open & close node
    O: recursively open node
    x: close parent of node
    X: close all child nodes of
       current node recursively
    middle-click,
    e: explore selected dir

    ----------------------------
    Bookmark table mappings~
    double-click,
    o: open bookmark
    t: open in new tab
    T: open in new tab silently
    D: delete bookmark

    ----------------------------
    Tree navigation mappings~
    P: go to root
    p: go to parent
    K: go to first child
    J: go to last child
    <C-j>: go to next sibling
    <C-k>: go to prev sibling

    ----------------------------
    Filesystem mappings~
    C: change tree root to the
       selected dir
    u: move tree root up a dir
    U: move tree root up a dir
       but leave old root open
    r: refresh cursor dir
    R: refresh current root
    m: Show menu
    cd:change the CWD to the
       selected dir
    CD:change tree root to CWD

    ----------------------------
    Tree filtering mappings~
    I: hidden files (off)
    f: file filters (on)
    F: files (on)
    B: bookmarks (off)

    ----------------------------
    Custom mappings~

    ----------------------------
    Other mappings~
    q: Close the NERDTree window
    A: Zoom (maximize-minimize)
       the NERDTree window
    ?: toggle help

    ----------------------------
    Bookmark commands~
    :Bookmark <name>
    :BookmarkToRoot <name>
    :RevealBookmark <name>
    :OpenBookmark <name>
    :ClearBookmarks [<names>]
    :ClearAllBookmarks

## Using bookmarks

    # move to a directory where you want to bookmark
    :Bookmark name
    # To display bookmarks
    B

## Display hidden files and directory

`shift``i`

## Using a mouse

Add the following to your .vimrc.

    " For mouse click in NERDTree
    :set mouse=a
    let g:NERDTreeMouseMode=3 

## Changing current working directory

    # check your pwd/current working dir
    :pwd
    # go to a directory in NERDTree and change the working directory
    cd
    # display only your working directory
    C
