# Bandit Level 8 → Level 9

## Level Information
- **Level:** 8 → 9
- **Username:** bandit8
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.

## Solution Steps

### 1. Connect to Bandit8
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls
```
Output: data.txt
### 3. Find the Unique Line
Use sort and uniq -u to find the line that appears only once:
```bash
sort data.txt | uniq -u
```
Output: Contains the password for bandit9
### Commands Used

    - ls - List files in directory

    - sort data.txt | uniq -u - Sort file and find unique line

## Important Concepts
## The sort Command

    - sort arranges lines in alphabetical/numerical order

    - Necessary before using uniq as it only detects adjacent duplicates

## The uniq Command

    - uniq -u displays only unique lines (that appear exactly once)

    - Requires sorted input to work correctly

    - Without -u flag, it removes duplicate lines

## Pipe Operator

    - | passes output from one command to another

    - Creates a pipeline for data processing
