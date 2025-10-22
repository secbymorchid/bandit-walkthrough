# Bandit Level 4 → Level 5

## Level Information
- **Level:** 4 → 5
- **Username:** bandit4
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the only human-readable file in the `inhere` directory.

## Solution Steps

### 1. Connect to Bandit4
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
### 2. Navigate to the inhere Directory
```bash
cd inhere
```
###  3. List All Files
```bash
ls -a
```
output : 
. -file00  -file02  -file04  -file06  -file08
..  -file01  -file03  -file05  -file07  -file09
### 4. Identify the Human-Readable File
Use the file command to check file types: 
```bash
file ./*
```
Output:
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
### 5. Read the Human-Readable File
Since the filename starts with -, use proper syntax:
```bash
cat -- "-file07"
```
Output: Contains the password for bandit5
## Commands Used 
    - ls -a - List all files

    - file ./* - Check file types of all files

    - cat -- "-file07" - Read the human-readable file with proper syntax
### Important Concepts
## Identifying File Types
    - Use file command to determine file format

    - "ASCII text" indicates human-readable content
     
    -  "data" typically means binary or non-text files











