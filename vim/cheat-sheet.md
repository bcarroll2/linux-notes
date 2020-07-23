# Vim Cheat Sheet

A collection of useful commands (and some alternatives) taken from `vimtutor` 
and https://www.youtube.com/watch?v=d8XtNXutVto&feature=youtu.be

 
### Moving Your Cursor
* `hjkl` - left/down/up/right
* `Shift+{` - up a paragraph
* `Shift+}` - down a paragraph
* `Ctrl+u` - up half a page
* `Ctrl+d` - down half a page
* `w` - move forward a word
* `b` - move back a word

### Exiting Vim
* `:q!` or `Shift+ZQ` - Quit without saving
* `:wq` or `Shift+ZZ` or `:x` - Save changes and quit

### Saving
* `:w` - saves current file, without quitting

### Deletion
* `x` - Delete character underneath cursor
* `dw` - Delete word (cursor must be at start of word)
* `d$` or `D` - delete from cursor to end of line
* `dd` - delete a whole line
* `daw` - delete around word (including space around)
* `diw` - delete inside word (not including space around)
* `D` - delete to end of line
* `c` - deletes and enters into insert mode
* `C` -delete to end of line and enter insert mode

### Insertion
All commands enter `insert` mode

* `i` - insert character to left of cursor
* `a` - insert character to right of cursor
* `I` - insert character to beginning of line
* `A` - inset character to end of line

press `esc` to exit insert mode

### Put/Paste
* `p` - puts the previous deleted line below cursor

### Undo/Redo
* `u` - undo previous change
* `U` - undo whole line
* `Ctrl+r` - redo

### Focusing Text
* `zz` - Center current line
* `zt` - Put current line at top
* `zb` - Put current line at bottom

### Surround Text
#### `ciw'Ctrl+r"'`
- `ciw` deletes the word the cursor is on, and enters insert mode!
- `'` adds a literal `'` character because you're in insert mode
- `Ctrl+r"` - Inserts the content of the `"` register (what you just yanked with ciw)
- `'` - the closing `'` character in insert mode.

