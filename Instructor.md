# Advanced command line instructor
 - Introduce yourself
 - Describe the class
 - Ask the students about themselves and what they expect or want from the class

## Command line
 - talk about the three outputs from a command
 - talk about the PATH variable and how it is used
 - talk about how to run a problem not on the PATH
 - talk about tab completion
 - piping and redirection

## BASH shortcuts
 - Refer the students to the bash shortcuts.
 - Talk about the various command editing shortcuts and let students try a few to get a feel.
 - Talk about the command history, have the students type history and look at its contents.
   - have the students try command-r to search backwards
   - try the Ctrl-p or up-arrow sequence
   - try the Ctrl-n or down-arrow sequence
   - try the Alt-. sequence to get the last word of the previous command
   - talk about the Ctrl-o and its use to repeat a sequence of commands

## Command Control Shortcuts
 - talk about the Ctrl-l sequence to clear the screen
 - talk about using Ctrl-s and Ctrl-q to control the flow of text in something that is spewing a lot of text. Also talk about `less` as an alternative.
 - Talk about foreground and background tasks and using Ctrl-z to put something in the background, and using fg to move it back to the foreground

## Bash Bang (!) commands
 - Demonstrate the run last command `!!`
 - Demonstrate the run most recent command that starts with 'blah'
 - Talk briefly about the other commands

## String substitution
 - briefly discuss the ^xxx^ syntax

## Using Editors for command line Editing
 - describe the two methods, Ctrl-x,Ctrl-e or fc and the difference. _hint, fc copies in the last command_

# grep
 - discuss the basic command line for grep
 - `grep <pattern> [filename or directory]`
 - `grep [options] -f [file]` [filename or directory]

There are four match type selections
 1. -E extended regular expressions
 2. -F fixed strings, seen as list of strings. This is best used with a file (-f filename)
 3. -G basic regular expressions (Default)
 4. -P use Perl-compatible expressions

Show -F using a temporary file
```
nano -w grepsea.txt
```
Enter a couple of search strings. Make sure that you don't include a new line at the end
`Ctrl-x` to exit
Then enter the following command

`grep -f grepsea.txt`

Try some following commands

`grep -r "Tab"`

which will search all folders from the CWD on down.

# Discuss file permissions
 - what does all of the symbols in the directory listing mean?
 - who owns the file?
 - what is group and how does that impact the file?
 - How to use chmod/chown/chgrp

# find/locate
Find and locate are two commands for finding files on the computer.
 - `locate` is a simple program but uses a database of file names rather than looking at the directory.
   - `locate [OPTION]`... PATTERN...
   - PATTERN can contain * as a character to represent any set of characters and can appear anywhere in the PATTERN
   - if there are no * characters then it is assumed that the pattern is *PATTERN*
   - if you specify --regex then the pattern is defined in regular expressions
   - you may have more than one pattern
   - use the following examples
     - `locate -b bash`
     - `locate -b '/bash'`
   - There are a variety of other options

- `find` is a command to find files in a more complicated manner
  - `find [options] [starting point] [expression]`
  - talk about positional options that look at date and time
    - `-amin`, `-atime`, `-cmin`, `-ctime`, `-mmin`, `-mtime`, for access minutes ago, access hours ago, status change minutes and hours, and modified
    - there is also `-cnewer`, `-anewer`, and `-newer` with a file as the argument for changed newer than the file or accessed newer than the file, or modified newer than file.

  - `-maxdepth`, `mindepth` control the depth one looks
  - `-lname` and `-iname` have a PATTERN as the argument and matches case sensitive or case insensitive. You can use * for any set of characters or ? to represent any character.
  - `-path` and `-ipath` are similar to name but use path.
  - `-regex` and `iregex`
  - __actions__
    - `-delete` deletes the file
    - `-exec command ;` and `exec command '{}' +` executes the command with arguments until ; is found or in the second variation executes the command with {} as the file name. This is powerful in combination with grep if the grep command does not allow selection of the correct group of files.
    - various printing commands line `-ls` `-print`

## rsync
`rsync` is used to synchronize files between two locations

`rsync [OPTION..] SRC... [DEST]`

If you don't use the [DEST] option then it only lists the files.

It can connect to remote servers either using ssh or rsh protocols or to an rsync daemon.

 - use the example `rsync -av class/html/* docs/`
 - modify one of the files in class/html
 - repeat the command and see what was transferred

There is a lot more to understanding rsync, so try it out and look at the man pages.

## Scripts
Talk a little about scripts, how to read the if then else fi and while|for|until do done constructs.
