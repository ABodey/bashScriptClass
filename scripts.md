# scripts

Scripts can be in a variety of languages, but most often you are going to find them written for the shell, in our case bash.

The first line of a bash script looks like
```
!#/bin/bash
```

After that the lines are commands that could be executed on the command line. Some specific features of the scripts are:

## if-then-else-fi
These statements allow for testing and control of the execution of the programs.

An example of this is
```
# exists test
filenm=$1
if [ -e $filenm ]
then
  echo "file $filenm exists"
else
  echo "file $filenm does not exist"
fi
```

## loops
there are three different kind of loops
### for loops
The important part of this is the `for`, `in`, `do` and `done`. The loop within the `do` and `done` are executed for each of the items following `in` and those values are assigned to the variable `lvar`.
```
# simple for loops
for lvar in "One" "Two" "Three" "Four"
do
  echo $lvar
done
```

An example of directory listing by passing in a path bash takes a creates a list of all the files and uses that for the loop.
```
echo ; echo "Listing"
for  fvar in scripts/*sh
do
  echo $fvar
done
```

## while loop
As long as the test is true the loop will execute.
```
# while loop
nmax=5
n=2
echo "loop from $n to $nmax"
while [ "$n" -le "$nmax" ]
do
  echo -n "$n " # -n to suppress newline
  n=$(($n+1))
done
```

## until loop
Replace the while with until in the example above and change the test appropriately and it will work the same.

## Full example
This shows loops, break and continue, and if statements.

```
#!/bin/bash

# break and continue
nmax=10
n=0

echo
echo "print numbers from 1 to 10 but exclude 4 and 6, stop after 8"
while (( n < nmax ))
do
  n=$(($n+1))
  if [ $n -eq 4 ] || [ $n -eq 6 ]
  then
    continue
  fi
  if [ $n -ge 9 ]
  then
    break
  fi
  echo -n "$n "
done
echo
```
