# Bandit Level 2 → Level 3

## Level Information
- **Level:** 2 → 3
- **Username:** bandit2
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in a file called `spaces in this filename` located in the home directory.

## Solution Steps

### 1. Connect to Bandit2
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
### 2. List All Files in Home Directory
```bash
ls -a
```
Output : 
```bash
.  ..  .bash_logout  .bashrc  .profile  --spaces in this filename--
```
### 3. Read the File with Spaces in Filename

Since the filename contains spaces, we need special syntax:

Method 1: Using quotes
```bash
cat -- "--spaces in this filename--"
```
Method 2: Using relative path
```bash
cat ./"--spaces in this filename--"
```
Output: Contains the password for bandit3 
## Commands Used

    - ls -a - List all directory contents

    - cat -- "--spaces in this filename--" - Read file using -- to handle leading dashes

    - cat ./"--spaces in this filename--" - Read file using relative path
### Important Concepts
## Dealing with Filenames Starting with --
   
    - Files starting with -- are problematic because -- is used to signal end of command options

    - Using -- before the filename tells the command to treat everything after as filenames, not options

    - Using ./ prefix also solves this issue by making it a path rather than just a filename






