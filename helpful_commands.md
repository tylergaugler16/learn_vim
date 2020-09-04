# Helpful Commands

## General 
Many commands follow a format:
command + motion

example: dw
command = d (delete)
motion = w (word)

You can also put a number before a motion to repeat it:
2w - navigate two words
d5w - delete five words


### Motions
w = word(including the proceding space) 🔥
b = back a word(excluding the preceding space)
e = word(exlcuding the proceding space)
$ = end of line
0 = begginning of the line
G = end of file
gg = begginning of the file

## Text Editing Commands
These only work when you are in "Normal" mode

### Deletion Commands
 
* dw - delete word
* d$ - delete to the end of the line
* de - delete word(but only to the end of the current word, as in it wont delete the proceding space)
* d0 - delete to the begginning of the line
* dd - delete to the end of the line(this is a default shortcut) 🔥
* x - delete a single character(i guess this doesnt follow a pattern lol)

### Undo Commands
u - undo last change 🔥
Ctrl-r - Redo changes which were undone (undo the undos) 🔥
U - return the last line which was modified to its original state (reverse all changes in last modified line)

### Put Command
p - puts the the previously deleted text after the cursor 🔥

To do this, use dd to delete a line, and use p to put it where you want

### Replace Command
r + [character you want to be used to replace] - replaces cursor with character chosen

ex: ra will replace the current charcter with an a

### Change Operator
_not sure why operator vs command_

ce [text] - *change* to the *end* of the word
_this brings you to interactive mode so you'll have to remember to go back to normal_

You can specify an optional number as well
c [number] motion
ex: c2e - change to the end of 2 words


### Movements
ctrl d - move down half the page 🔥
ctrl u - move up half the page 🔥

ctrl g - will show you your location in the filer
number G - will go to line [number] of the file

### Search 🔥
/ text - will search file for text

To search the same phrase again, simply type n
To search the same text again in the opposite direction, type N

? text - will search file for text(in the opposite direction)

To go back where you came from press ctrl-o


### Matching Parentheses Search
When the cursor is on any opening parentheses, type % to move to it's closing

### Find and substitute
:s/old/new - this will replace first occurance of old with new
:s/old/new/g = this will replace all occurances of old with new on the same line. (g is for global)
:#,#s/old/new/g - where the # are line numbers. replaces all occurances within the line numbers
:%s/old/new/g - this will replace every instance in the whole file 🔥
:%s/old/new/gc - this will replace every instance in the whole file, but prompt whether or not you want to change each time 🔥


### Writing Files
:!ls - to get a listing of your current directory
:w FILENAME - to save the current file as FILENAME in the current directory
:!rm FILENAME - to delete FILENAME in the current directory

_using !: seems to just run a command in the terminal_


### Writing a portion of content to a new file
1) Press v _(this enteres visual mode.. which seems to just be be "selection" mode)_
2) Press :v FILENAME

### Retrieving content from another file
:r FILENAME - puts the content of FILENAME where the cursor is

*Note: You can also use this to read output from an external command. For exampe, :r !ls will put the content of of ls command where the cursor is *

### Open Command
o - will put an extra line below the cursor
O - will put an extra line above the cursor

### Append Command
a - will go to the next character and enter Insert mode
A - will go to the end of the line and enter Instert mode

### Replace Command
R - will enter into Replace mode, which is like Insert mode, but every character typed will overrite the existing one. 

### Copy and Paste
1) Use v(Visual mode) to select text
2) Press y to copy
3) Go to the place you want to paste, and press p

### File Managment
Working with large projects

#### Buffers
:e path/to/file - will open up the specified file in a new buffer
:buffers - will list the current buffers (and show the buffer number for each)
:b2 - will go to the file in the second buffer. Works for all numbers



### Plugins

#### ["tpope/vim-rails"](https://github.com/tpope/vim-rails)
gf - when the cursor is over any identifier (model, controller, etc) and it will jump to it 🔥
