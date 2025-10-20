# Bandit Level 1 → Level 2

## Level Information
- **Level:** 1 → 2
- **Username:** bandit1
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in a file called `-` located in the home directory.

## Solution Steps

### 1. Connect to Bandit1
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls -a
```
Output: 
```bash
-  .  ..  .bash_logout  .bashrc  .profile
```
### 3. Read the Special Filename
Since the filename is - (a dash), we need special syntax to avoid it being interpreted as a command option:
```bash
cat ./-
```
Output: Contains the password for bandit2
## Commands Used

    - ls -a - List all directory contents (including hidden files)

    - cat ./- - Read file with special filename - using path notation
### Important Concepts
## Dealing with Special Filenames

    - Files named - are problematic because - is normally used for command options

    - Using ./- tells the system to treat - as a filename, not an option

    - The ./ prefix specifies the current directory explicitly
