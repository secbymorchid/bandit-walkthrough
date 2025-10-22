# Bandit Level 7 → Level 8

## Level Information
- **Level:** 7 → 8
- **Username:** bandit7
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the file `data.txt` next to the word `millionth`.

## Solution Steps

### 1. Connect to Bandit7
```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls -a
```
Output: .  ..  .bash_logout  .bashrc  data.txt  .profile
### 3.Search for the Password Next to "millionth
Use grep to find the line containing "millionth":
```bash
grep "millionth" data.txt
```
Output: Contains the password for bandit8
### Commands Used

    - ls -a - List all files including hidden ones

    - grep "millionth" data.txt - Search for the word "millionth" in data.txt

## Important Concepts
## The grep Command

    - grep searches for patterns in files

    - Returns lines that match the specified pattern

    - Case-sensitive by default (use -i for case-insensitive)

    - Can use regular expressions for complex pattern matching
