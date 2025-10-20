# Bandit Level 3 → Level 4

## Level Information
- **Level:** 3 → 4
- **Username:** bandit3
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in a hidden file in the `inhere` directory.

## Solution Steps

### 1. Connect to Bandit3
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
### 2. List Contents of Home Directory 
```bash
ls -a
```
Output:
```bash
.  ..  .bash_logout  .bashrc  inhere  .profile
```
### 3. Navigate to the inhere Directory
```bash
cd inhere
```
### 4. List All Files (Including Hidden Ones)
```bash
ls -a
```
Output:
```bash
.  ..  ...Hiding-From-You
```
### 5. Read the Hidden File

The file starts with dots which can be confusing. Use one of these methods:

Method 1: Using -- to handle special filenames
```bash
cat -- "...Hiding-From-You"
```
Method 2: Using proper path syntax
```bash
cat ./"...Hiding-From-You"
```
Output: Contains the password for bandit4

## Commands Used

    - ls -a - List all files including hidden ones

    - cd inhere - Change to the inhere directory

    - cat -- "...Hiding-From-You" - Correct way to read the file

    - cat ./"...Hiding-From-You" - Alternative correct method

### Important Concepts
## Handling Files Starting with Dots

    - Files starting with multiple dots (...) are not traditional hidden files

    - They can be confusing to work with in commands

    - Use -- to indicate end of options, or ./ prefix to specify it's a file






