|command| description|
|----|----|
|0 (command mode)| Move to the top of file|
|0 (normal mode) | Move to the start of line|
|$| Move to the end of file (cursor at the first char of line)|
|$ (normal mode)| Move cursor to the end of line  | 
|tabnew| Open file in new tab|
|tabn| Go to next tab|
|tabp| Go to previous tab|
|tabc| Close current tab|
|Ctrl + r| Redo|
|u| Undo|
|%d| delete all lines|
|%y| yank all |
|suspend|supended| 
|>>| Indent line by shiftwidth spaces|
|<<|De-indent line by shiftwidth spaces|
|5>>|Indent 5 lines|
|5==|Re-indent 5 lines|
|ma| Mark top of block to indent as marker 'a'|
|set nonumber|hide line number|
|set list|display tab and EOL|
|Ctrl + v| visual block (for making changes in block)| 
|\\<term\\>|To search an exact term|
|\* (cursor at the search word)|To search an exact term| 
|o|Insert a line after current line|
|O|Insert a line before current line|
|set textwidth=80| wrap at 80 characters per line|
|set colorcolumn=80| mark the column 80 character|
|ma (in normal mode)| mark the line cursor is at as a|
|\`a (in normal mode)| jump back to mark a|
|\`.(in normal mode)| jump to the last edit line and column|
|\`"(in normal mode)| jump to the last position of cursor where you exited the previous session|
|marks|show all mark set|
|H| move cursor to the top of view port|
|M| move cursor to the middle of view port|
|L| mover cursor to the bottom of view port|
|e| open file from buffer|
|ls| display a list of currently opened files in buffer|
|n| go to next file|
|N| go to previous file|
|bd| closes the buffer|
|Ctrl + n (insert mode) | Get list of word suggestion |
|%s/pattern 1/pattern 2/g | Search pattern 1 throughout whole file and replace with pattern 2|
|r! command (command mode)|Insert shell command output to file content|
|set all| For a list of all current settings|
|h \<option> (command mode)| Help manual|
|CTRL G|Show the column current cursor is at|    
|set ruler | Set the ruler |
|in visual mode, type u | turn to lowercase for the visual part|
|in visual mode, type U| turn to uppercase for the visual part|
|A|append to the end of line|
|a|append to the end of word|
|dw| move cursor to the beginning of the word to delete the whole word|
|d$|delete to the end of line| 
|0| move to the start of line|
|\<#>w| move cursor\<#> number of word forward|
|\<#>e| move cursor to the end of \<#> number of word forward|
|U| undo changes on the whole line|
|R| replace more than one character|   
|r| replace the character cursor at by a charater you type| 
|ce|change unitl the end of a word|
|CTRL + O| go back to where your search starts|
|%| find matching ), ], } |
|%s/old/new/gc| find every occurrence in the whole file with a prompt whether to subsitute or not|
|#,#s/old/new/g| #, # are the line number of the range of line to subsitute|
|!\<shell cmd>| execute external shell command|
|v, :w \<filename>| to save part of the file|
|:r \<filename> | to retrieve file content| 
|CTRL W| to jump from one window to another| 
|browse oldfiles| get a history of recent open files|   
|:goto \<character index>| move cursor to the character position|
|g CTRL-G| show line status|









