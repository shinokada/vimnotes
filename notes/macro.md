# Macro 

## Record
`q{register}` to start recording and `q` to stop.

    qa # start recording into register 'a'
    A;<Esc> # Append ; and escape
    Ivar <Esc> # `I` to go to the beginnin and change to Insert mode and enter var and escape.
    q # to stop recording
    # check the register 'a'
    :reg a 
    # notice ^[ is the same as <Esc>

## Play back

    @{register}
    ## repeat the last macro invoked
    @@

    j
    @a
    j@@ # repeat the last macro invoked





