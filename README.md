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

### sort
#### to find unique line

`sort data.txt | uniq -u`

### grep

#### Regex search file

`cat file.ending | format | grep '[^character]*$'`

where ^ is the start of the line, * however many times, and $ means end of line.

### base64

#### Test whether data is base64 or not 

`cat name-of-file.extension-tipe | grep -E '[A-Za-z0-9+/]{4}*([A-Za-z0-9+/]{4}|[A-Za-z0-9+/]{3}=|[A-Za-z0-9+/]{2}==)'`

#### If true and have base64 tool

If the data is suspected to be encoded in base64 and there is the tool **base64** installed then to decode it do:
`bas64 -d -i name-of-file.extension_type`

where `-d` is to decode and `-i` is to ignore garbage such as newlines.

### tr

For translation or deleting of characters.

#### rot13
`cat datat.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`

