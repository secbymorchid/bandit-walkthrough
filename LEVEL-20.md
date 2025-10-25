# Bandit Level 19 → Level 20

## Level Information
- **Level:** 19 → 20
- **Username:** bandit19
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Solution Steps

### 1. Connect to Bandit19
```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls 
```
Output: bandit20-do
### 3. Understand the Setuid Binary
```bash
./bandit20-do
```
Output: Shows usage instructions
### 4. Check Effective User ID
```bash
./bandit20-do id
```
Output: Shows euid=11020(bandit20) - confirms it runs as bandit20
### 5. Read the Bandit20 Password
```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```
Output: Contains the password for bandit20
### Commands Used
- ls - List files in directory

- ./bandit20-do - Execute setuid binary to see usage

- ./bandit20-do id - Check effective user ID

- ./bandit20-do cat /etc/bandit_pass/bandit20 - Read password file with elevated privileges

## Important Concepts
### Setuid Binaries
- Setuid (Set User ID) allows a program to run with the privileges of the file owner

- euid=11020(bandit20) shows effective user ID is bandit20

- Allows accessing files owned by bandit20 user

- Security feature that must be used carefully



