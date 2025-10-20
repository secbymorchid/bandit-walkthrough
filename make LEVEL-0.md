# Bandit Level 0 → Level 1

## Level Information
- **Level:** 0 → 1
- **Username:** bandit0
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in a file called `readme` located in the home directory. Use this password to log into bandit1 using SSH.

## Solution Steps

### 1. Connect to Bandit0
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls
```
- Output: readme

### 3. Read the Password File
```bash
cat readme
```
- Output: Contains the password for bandit1

## Commands Used
-  ls - List directory contents
 - cat - Display file contents

## Important Notes

 - Save the password found in readme to your local machine

- Use the password to log into bandit1 via SSH on port 2220

- Passwords are not saved automatically - keep your own notes

 ##TIP 
 - Create a secure file on your local machine to store all level passwords and solution notes!

-  Passwords may change, so document your solution process
