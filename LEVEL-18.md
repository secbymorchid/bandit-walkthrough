# Bandit Level 17 → Level 18

## Level Information
- **Level:** 17 → 18
- **Username:** bandit17
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
There are 2 files in the homedirectory: `passwords.old` and `passwords.new`. The password for the next level is in `passwords.new` and is the only line that has been changed between the two files.

## Solution Steps

### 1. Connect to Bandit17
```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220
```
### 2. Compare the Two Password Files
```bash
diff passwords.old passwords.new
```
Output: Shows the changed line containing the password for bandit18
### Commands Used

    - diff passwords.old passwords.new - Compare two files and show differences

## Important Concepts
### The diff Command

    - diff compares files line by line

    - Shows which lines differ between files

    - Useful for finding changes in configuration files, code, or data

    - Output format: < for first file, > for second file
