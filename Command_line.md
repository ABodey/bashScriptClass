# Command line

The command line is where commands can be executed in a bash shell inside a terminal

## Output
A command has three outputs
 1. standard output where most output goes
 2. error output where errors go, if not redirected it appears mixed in the standard output (or seemingly so)
 3. the return value which is normally only used in scripts

## PATH
The shell variable PATH holds the locations that all commands are looked for in the order of the PATH.

## Tab Completion
Tab completion works in Linux in two ways.

1. At the command line start.

   Start typing and then hit tab and it will prompt with possible commands that you can use. It searches the path for commands starting with the characters you type.

   If there is not a single match then nothing happens, hitting tab again shows all the possibilities.

   If the number of possibilities is large it will prompt before displaying them.

   It will then bring you back to the prompt so you can continue.

3. In the middle of a command, the shell looks in the current directory for possible file names beginning with the characters.

    If there are none nothing happens. If there are a small number then it shows a list like the one above.

## Piping and redirection
The pipe character `|` is used to take the standard output and use it as the standard input for the command following the `|`.
 - show and example of a pipe command

 - The `>` character redirects the standard output to the file specified after.
 - The `2>` sequence redirects the standard error output to the file specified after.
 - The `>>` sequence redirects the standard output and appends to the file after.
 - The `2>>` sequence redirects the standard error and appends to the file after.
 - The `<` redirects standard input to the file specified after.
