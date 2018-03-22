# find and locate
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
