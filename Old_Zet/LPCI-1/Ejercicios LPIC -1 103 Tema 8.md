**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. vi is most used as an editor for configuration files and source code, where indentation helps to identify sections of text. A selection can be indented to the left by pressing < and to the right by pressing >. What keys should be pressed in normal mode to indent the current selection three steps to the left?
- R:  3<
##### 2. An entire line can be selected by pressing V in vi normal mode. However, the terminating newline character is also included. What keys should be pressed in normal mode to select from the starting character until, but not including, the newline character?
- R: 0v$h
##### 3. How should vi be executed in the command line to open ~/.bash_profile and jump straight to the last line?
- R: vi + ~/.bash_profile
##### 4. What keys should be pressed in vi normal mode to delete characters from the current cursor position until the next period character?
- R: dt.
# Explorational Exercises
##### 1. vim allows to select blocks of text with arbitrary width, not only sections with entire lines. By pressing Ctrl + V in normal mode, a selection is made by moving the cursor up, down, left and right. Using this method, how would a block starting at the first character in the current line, containing the next eight columns and five lines of text, be deleted?
- R:  0, Ctrl-V and 8l5jd
##### 2. A vi session was interrupted by an unexpected power failure. When reopening the file, vi prompts the user if they want to recover the swap file (an automatic copy made by vi). What should the user do to discard the swap file?
- R: Press d when prompted by vi.
##### 3. In a vim session, a line was previously copied to the register l. What key combination would record a macro in register a to paste the line in register l immediately before the current line?
- R:  The combination qa"lPq, meaning q (“start macro recording”), a (“assign register a to macro”), "l (“select text in register l”), P (“paste before the current line”) and q (“end macro recording”).
- - - 
## ***Sources:***