# Bandit Level 10 → Level 11

## Level Information
- **Level:** 10 → 11
- **Username:** bandit10
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the file `data.txt`, which contains base64 encoded data.

## Solution Steps

### 1. Connect to Bandit10
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls 
```
Output: data.txt
### 3. Decode the Base64 Data
Use base64 -d to decode the file:
```bash
base64 -d data.txt
```
Output: Contains the password for bandit11
## Commands Used

    - ls - List files in directory

    - base64 -d data.txt - Decode base64 encoded file

## Important Concepts
## Base64 Encoding

    - Base64 is a method for encoding binary data as ASCII text

    - Commonly used for email attachments, web data, and storing binary in text formats

    - Uses 64 characters (A-Z, a-z, 0-9, +, /) and = for padding

## The base64 Command

    - base64 -d decodes base64 data back to its original form

    - Without -d flag, it encodes data to base64

    - Can read from files or standard input
