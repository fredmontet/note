VIM
===

Copy paste from Vim
-------------------

    v motion   Select what you want
    d          Cut 
    y          Copy (yank)
    yw         Copy one word
    yy         Copy one line
    p          Paste

Commands
--------

### Delete

    x	       delete the char under the cursor
    dd         delete the line

### Undo/Redo

    u          undo
    U          undo all changes on a line
    ctrl+r     redo
    p          put a line stored in a vim register (e.g. after add)
    
### Append, etc.

    a          append after the cursor
    A          append at the end of the line
    r          replace one char (e.g rx replace char by x)
    R          replace many chars

### New lines

    o          Add a line below the cursor and start INSERT mode
    O          Add a line above the cursor and start INSERT mode

Operators
---------

    d          Delete operator
    c          Change operator

Motion
------

    w		until the start of the next word, EXCLUDING its first character.
    b		same as w but backward
    e		to the end of the current word, INCLUDING the last character.
    $		to the end of the line, INCLUDING the last character
    0           to the beginning of the line

    exemple:

      d$      To delete to the end of the line
      d2w     To delete the next two 2 words
      2w      To move the cursor at the beginning two word forward
      2e      To move the cursor at the end two word forward
      2dd     To delete the two next lines

Cursor Location
---------------

    Ctrl-g    Cursor location and file status

    $$ G      Move to the line number $$
    gg        Move to the beginning of the file
    G         Move to the end of the file


Search Command
--------------

    Type / followed by the query to search forward
    Type ? followed by the query to search backward

    n        Go forward to the next occurance
    N        Go backward to the next occurence       

    Ctrl-o   Go back 
    Ctrl-i   Go further


Matching Parenthesis Search
---------------------------

    Type % to find a matching ), ] or }
    The cursor will move to the next, or previous, parenthesis


Substitution Command
--------------------

    :s/old/new to replace the first occ. of old by new
    :s/old/new/g to replace all occ. in the line
    :%s/old/new/g for all occ. in the file
    :#, #s/old/new/g to change multiple lines

    Add c at the end e.g. :s/old/new/gc to have a confirmation prompt


External Command
----------------

    You can execute any external commands with

    :! my_command


Visual Mode
-----------

    v        visual mode used for selection with motion
    
    For instance with v, then selecting and :w my_file.txt to save the
    selection somewhere.


File Related Commands
---------------------
    
    :w FILENAME      Save a file somewhere
    :r FILENAME      Retrieve a file and put the content at cursor pos.
    :r !ls           Retrieve also accepts terminal cmds


Set Options
-----------

    :set xxx         Sets the option 'xxx', for instance
                       - ic, ignorecase : ignore case while searching
                       - is, incsearch  : search partial matches
                       - hls, hlsearch  : highlight matches

    :set noxxx       Deactivates an option


Get help
--------

    :help w
    :help c_CTRL-D
    :help instert-index
    :help user-manual


Other
-----

    CTRL-D            Autocomplete commands like :help
    CTRL-W            Change window

