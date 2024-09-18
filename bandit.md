# Bandit Assignment Notes

Here are a few of the key ideas explored in the 34 bandit exercises:

- listing files and directories, including "hidden" ones (i.e., those whose names start with a period, like .gitignore or ..)    viewing the contents of files with cat, hexdump, editors like nano or vim, etc.
- filtering and transforming file contents with grep, sort, uniq, tr, hexdump, xxd, etc.
- public and private encryption keys (especially as used in logging into computers via SSH)
- services listening at particular TCP ports, and how to communicate with them
- compression utilities like zip/unzip, gzip/gunzip, bzip2/bunzip2, tar, etc.
- cron jobs
- bash scripts
- git

### Level 0

Password contained in README.

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

### Level 1

Password contained in a file titled "-", which is a special character refering
to stdin.

263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Specify the entire file like "cat ./-"

### Level 2

If a file contains spaces, specify the title as a string using " or '.

MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

### Level 3

The file was hidden because it begins with a '.'

These files can be revealed with the -a argument for ls.

2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

### Level 4

Several of the files just contained data while file07 contained ASCII text.

4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

### Level 5

There are many decoy files and directories. A simple (perhaps inefficient) way
to find the corrent file is searching through each directory using "ls -al"

HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

### Level 6

Navigated to the root directory and ran 'find -size 33c -user bandit7 -group
bandit6"

morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

### Level 7

cat data.txt | grep -i millionth

dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

### Level 8

Apparently we needed to sort the data before pulling out the unique row, which
does not make much sense to me since "uniq -u" should be able to do the trick.

sort data.txt | uniq -u

4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

### Level 9

### Level 10

### Level 11

### Level 12