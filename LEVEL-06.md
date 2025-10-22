# Bandit Level 5 → Level 6

## Level Information
- **Level:** 5 → 6
- **Username:** bandit5
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in a file somewhere under the `inhere` directory with these properties:
- Human-readable
- 1033 bytes in size
- Not executable

## Solution Steps

### 1. Connect to Bandit5
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```
#### 2. Navigate to the inhere Directory
```bash 
cd inhere 
```
### 3. Find the File with Specific Properties
Use the find command with multiple criteria
```bash
find . -type f -size 1033c ! -executable
```
Output: 
./maybehere07/.file2
### 4. Read the Found File
```bash
cat ./maybehere07/.file2
```
Output: Contains the password for bandit6
Commands Used

    cd inhere - Change to the inhere directory

    find . -type f -size 1033c ! -executable - Find file with specific properties

    cat ./maybehere07/.file2 - Read the password file

### Important Concepts

### The find command with multiple filters:

    - -type f - Search only for files (not directories)

    - -size 1033c - Find files exactly 1033 bytes in size (c = bytes)

    - ! -executable - Find files that are NOT executable
