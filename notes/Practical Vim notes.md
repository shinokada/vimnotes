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

