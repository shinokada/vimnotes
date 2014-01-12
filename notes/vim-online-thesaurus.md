# vim-online-thesaurus
[vim-online-thesaurus](https://github.com/beloglazov/vim-online-thesaurus)
## Usage

The plugin provides the `:OnlineThesaurusCurrentWord` command to look up the
current word under the cursor in an online thesaurus. Alternatively, you can
look up any word with `:Thesaurus word`.

Internally, both commands make a request to http://thesaurus.com/, parse the
results, and display them in a vertical split in the bottom.

By default the `:OnlineThesaurusCurrentWord` command is mapped to
`<LocalLeader>K`.  If you haven't remapped `<LocalLeader>`, it defaults to `\`.
To close the split, just press `q`.
