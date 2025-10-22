# Bandit Level 6 → Level 7

## Level Information
- **Level:** 6 → 7
- **Username:** bandit6
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored somewhere on the server and has these properties:
- Owned by user bandit7
- Owned by group bandit6
- 33 bytes in size

## Solution Steps

### 1. Connect to Bandit6
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
### 2. Search the Entire System for the File
Use the find command with multiple criteria and error suppression:
```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
Output: /var/lib/dpkg/info/bandit7.password
### 3. Read the Found File
```bash
cat /var/lib/dpkg/info/bandit7.password
```
Output: Contains the password for bandit7
## Commands Used

    - find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null - Search entire system with specific criteria

    - cat /var/lib/dpkg/info/bandit7.password - Read the password file

### Important Concepts
## System-Wide File Searching

The find command with advanced filters:

    - / - Search from root directory (entire system)

    - -type f - Search only for files

    - -user bandit7 - Files owned by user bandit7

    - -group bandit6 - Files owned by group bandit6

    - -size 33c - Files exactly 33 bytes in size

    - 2>/dev/null - Suppress permission denied errors
