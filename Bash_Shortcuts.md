# Command Editing Shortcuts

- **Ctrl + a** – go to the start of the command line
- **Ctrl + d** – exit bash (quit terminal)
- **Ctrl + e** – go to the end of the command line
- **Ctrl + k** – delete from cursor to the end of the command line
- **Ctrl + u** – delete from cursor to the start of the command line
- **Ctrl + w** – delete from cursor to start of word (i.e. delete backwards one word)
- **Ctrl + y** – paste word or text that was cut using one of the deletion shortcuts (such as the one above) after the cursor
- **Ctrl + xx** – move between start of command line and current cursor position (and back again)
- **Alt + b** – move backward one word (or go to start of word the cursor is currently on)
- **Alt + f** – move forward one word (or go to end of word the cursor is currently on)
- **Alt + d** – delete to end of word starting at cursor (whole word if cursor is at the beginning of word)
- **Alt + c** – capitalize to end of word starting at cursor (whole word if cursor is at the beginning of word)
- **Alt + u** – make uppercase from cursor to end of word
- **Alt + l** – make lowercase from cursor to end of word
- **Alt + t** – swap current word with previous
- **Ctrl + f** – move forward one character
- **Ctrl + b** – move backward one character
- **Ctrl + d** – delete character under the cursor
- **Ctrl + h** – delete character before the cursor
- **Ctrl + t** – swap character under cursor with the previous one

# Command Recall Shortcuts

- **Ctrl + r** – search the history backwards
- **Ctrl + g** – escape from history searching mode
- **Ctrl + p** – previous command in history (i.e. walk back through the command history)
- **Ctrl + n** – next command in history (i.e. walk forward through the command history)
- **Alt + .** – use the last word of the previous command
- **Ctrl + o** – used in history (up arrow) to execute the command and then recall the next command to execute.

# Command Control Shortcuts

- **Ctrl + l** – clear the screen
- **Ctrl + s** – stops the output to the screen (for long running verbose command) _this is a function of the terminal_
- **Ctrl + q** – allow output to the screen (if previously stopped using command above) _this is a function of the terminal_
- **Ctrl + c** – terminate the command
- **Ctrl + z** – suspend/stop the command _part of background/foreground_

# Bash Bang (!) Commands

- **!!** – run last command
- **!blah** – run the most recent command that starts with ‘blah’ (e.g. !ls)
- **!blah:p** – print out the command that !blah would run (also adds it as the latest command in the command history)
- **!$** – the last word of the previous command (same as Alt + .)
- **!$:p** – print out the word that !$ would substitute
- **!*** – the previous command except for the first word (e.g. if you type ``find some_file.txt /``, then !* would give you `some_file.txt`)
- **!*:p** – print out what !* would substitute

# String substitution
Uses the ^xxx^ syntax to find and replace with what follows the last ^

Example:
```
$ touch Grep.md
$ ^Grep^Tab_completion
touch Tab_completion.md
```

1. Created file `Grep.md` using touch
2. Replaced `Grep` in this command with `Tab_completion`
3. This executed the command `touch Tab_completion.md`

# Using editors for command line Editing
There are times that an editor is nice to work on a complicated command.

You can use two methods to get an editor, and the editor is your default
1. ctrl-x ctrl-e
2. fc
Note that you can enter more than one command in the editor if you want to execute multiple commands. These are not saved (except to a temporary file)

## References
* http://www.skorks.com/2009/09/bash-shortcuts-for-maximum-productivity/
