# useful-otw-bash-cmds
useful cmds / scripts


## Bash Code 

### How to loop over all files in a directory and `cat` their contents to the stdout

```cli
# Get the pwd
> pwd
> /home/bandit4/inhere

# Set the file paths
> FILES=/home/bandit4/inhere/-file*

# Iterate over the files looking for the plaintext pwd
> for f in $FILES; do echo "Cating file $f"; cat $f; done
```
### find
#### Check that a file is x size, text readable, and whether it is executable or not 

```cli
> find . -type f -size 1033c ! -executable -exec sh -c 'file -b $0 | grep -q text' {}\; -print
```

`find` looks in the current directory for all files of type 'f' with size equal to 1033 bytes (c suffix) and that are not executable, then run the exec command to see what type of file it is (text or not). 

#### find file by size, owner, and group owners

`find / -size 33c -type f -user bandit7 -o -group bandit6`

#### find line with word

`find / -name "the-word-to-be-found" name-of-file.txt`
