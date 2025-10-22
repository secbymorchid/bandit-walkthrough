# Bandit Level 9 → Level 10

## Level Information
- **Level:** 9 → 10
- **Username:** bandit9
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several '=' characters.

## Solution Steps

### 1. Connect to Bandit9
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls -a 
 ```
Output: . .. .bash_logout .bashrc data.txt .profile
### 3. Extract Human-Readable Strings and Search for '='
Use strings to find readable text and grep to filter lines with '=' characters:
```bash
strings data.txt | grep "="
```
Output: Contains the password for bandit10 preceded by '=' characters
### Commands Used

    - ls -a - List all files including hidden ones

    - strings data.txt - Extract human-readable strings from binary file

    - grep "=" - Filter lines containing '=' characters

## Important Concepts
### The strings Command

    - strings extracts printable character sequences from binary files

    - Useful for finding hidden text in executables or data files

    - Default minimum length is 4 characters

### Pattern Matching with grep

    - grep "=" searches for lines containing the '=' character

    - The password is preceded by multiple '=' characters as a visual marker

    - Helps identify the relevant line among extracted strings
