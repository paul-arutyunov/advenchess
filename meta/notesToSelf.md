## about loading sprites during VBlank:
vsync is more than 1024 mcycles. this is ~14 tiles.
right now the code assumes there are less than 14 tiles to load.
so, one VBlank would be enough for that...
## about entry point:
instead of jumping to start, and then calling all the init
things,	should use ROP - `ld sp, Table; ret` where Table is an
array of pointers to all the init functions, and then to a small
piece that just says `ld sp, stack_pos; jp start`
## number of objects:
using 32 objects instead of 40 allows me to allign the structs to
increase code speed
## multiplayer ideas:
the player AI would only need to change the input keys function
to work with multiplayer on sgb. link cable should also be
possible...
