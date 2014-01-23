# Practical Vim notes

## Ctrl-r{register}

In the insert mode use this to paste content from register 0 for example

    :h i_CTRL-R

    <C-r>0

## Delete, Yank and Put with unnamed register
### Transposing

    # transposing two characters
    xp # to cut and paste it after the cursor since it is a character-wise register.

    # transposing two lines, paste below the cursor line since it is a line-wise register.
    ddp

## Calculations 
Tip 16

    # Insert mode 
    <C-r>6*35<CR>

## Inserting unusual characters
Tip 18

    # Insert mode <C-v>code
    # <C-v>065 is A
    # For hexadecial use u after <C-v>
    # <C-v>u00bf is ¿

Use `ga` to see the character code under cursor.

    <C-v>{123}       # Insert character by decimal code
    <C-v>u{1234}     # Insert character by hexadecimal code
    <C-v>{nondigit}  # Isert nondigit literally	
    <C-k>{char1}{char2} # Insert character represente by digraph
    <C-k>I?
    <C-k>12
    <C-k>14

Check `:h digraphs-use` or `:h digraph-table`.

    # Insert mode <C-v>code
    # <C-v>065 is A
    # For hexadecial use u after <C-v>
    # <C-v>u00bf is ¿

Use `ga` to see the character code.

    <C-v>{123}       # Insert character by decimal code
    <C-v>u{1234}     # Insert character by hexadecimal code
    <C-v>{nondigit}  # Isert nondigit literally	
    <C-k>{char1}{char2} # Insert character represente by digraph
    <C-k>I?
    <C-k>12
    <C-k>14

Check `:h digraphs-use` or `:h digraph-table`.

