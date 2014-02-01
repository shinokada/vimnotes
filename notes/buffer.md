# Buffers

[Working with buffers](http://vimcasts.org/episodes/working-with-buffers/)

## Working with buffers

| command | action                                                                              |
|---------|----------------------------------------------|
|:l       | sshow the buffer list                                                               |
|:b       | nopen the next buffer in the current window (cycles from the end of the list to the beginning).|
|:bp      | open the previous buffer in the current window (cycles from the start of the list to the end).|
|CTRL-^   | Buffersswitch to the alternate file|

## Dealing with hidden buffers

|command | action|
|--------|--------------|
|:with   | save the changes to a file|
|:e!     | Buffersrestore the original file|
|:bd!    | Buffersforcibly remove the buffer from the buffer list, discarding any changes|
|:q!     | Buffersforce Vim to quit, discarding changes to all modified buffers|
