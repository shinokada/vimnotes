# TwitVim

[TwitVim](http://vim.sourceforge.net/scripts/script.php?script_id=2204)

My .vimrc.

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

## Using a browser
Add one of the following in .vimrc. Use `<Leader>g` for my case `\g` to open an URL. 

    # On OS-X
    let twitvim_browser_cmd = 'open'
    # Firefix
    let twitvim_browser_cmd = 'firefox.exe'
    # w3m
    let twitvim_browser_cmd = 'w3m'

If you are using w3m, [read this post](http://d.hatena.ne.jp/unarist/20110323/1300850441).

## Usage: 

    :PosttoTwitter # This command will prompt you for a message to send to Twitter. 
    :CPosttoTwitter # This command posts the current line in the current buffer to Twitter. 
    :BPosttoTwitter # This command posts the current buffer to Twitter. 
    
    Alt-T # In Visual select mode, the Alt-T key posts the selected text to Twitter. 
    (use Ctrl-T instead if menu bar is enabled) 
    # NOTE: The T mapping was changed to Alt-T to avoid overriding the T search command. 
    
    <Leader>r # or \r Starts a @-reply
    Alt-R # Starts a @-reply. (from timeline buffer) 
    Alt-D # Starts a direct message. (from timeline buffer) 
    <Leader>R # or \R to retweet
    <Leader><Leader> # or \\ to update
    <Leader>X # delete a tweet

    :FriendsTwitter # View friends timeline. 
    :UserTwitter # View your timeline. 
    :MentionsTwitter # View @-mentions. 
    :PublicTwitter # View public timeline. 
    :DMTwitter # View direct messages. 
    
    :Tweetburner # Shorten a URL with Tweetburner and insert at cursor. 
    :ATweetburner # Same as above but insert after cursor. 
    :PTweetburner # Same as above but start tweet on cmdline with short URL. 
    
And similar commands for TinyURL, SnipURL, Metamark, bit.ly, goo.gl, rga.la, is.gd, urlBorg, tr.im, Cligs, and zi.ma. 

    :SearchTwitter # Use Twitter Search. 

