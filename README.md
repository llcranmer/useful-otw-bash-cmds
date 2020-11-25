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
