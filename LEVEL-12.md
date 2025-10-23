# Bandit Level 11 → Level 12

## Level Information
- **Level:** 11 → 12
- **Username:** bandit11
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Solution Steps

### 1. Connect to Bandit11
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls
```
Output: data.txt
### 3. Decode the ROT13 Text
Use tr to rotate the letters by 13 positions:
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
Output: Contains the password for bandit12
## Commands Used

    - ls - List files in directory

    - cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' - Decode ROT13 encoded text

### Important Concepts
## ROT13 Cipher

    - ROT13 is a simple letter substitution cipher

    - Each letter is rotated 13 positions in the alphabet
    
    - A → N, B → O, ..., Z → M (same for lowercase)

    - ROT13 is its own inverse (applying twice returns original text)

## The tr Command

    - tr translates or deletes characters

    - 'A-Za-z' 'N-ZA-Mn-za-m' maps A→N, B→O, ..., M→Z, N→A, etc. 
    
    - Can be used for various character substitution task
