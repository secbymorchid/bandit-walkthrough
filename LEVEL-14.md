# Bandit Level 13 → Level 14

## Level Information
- **Level:** 13 → 14
- **Username:** bandit13
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user bandit14. You get a private SSH key that can be used to log into the next level.

## Solution Steps

### 1. Connect to Bandit13
```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
### 2. List Files in Home Directory
```bash
ls
```
Output: sshkey.private
### 3. Use SSH Key to Connect to Bandit14
```bash
ssh -i sshkey.private bandit14@localhost
```
#### 4. Read the Bandit14 Password
```bash
cat /etc/bandit_pass/bandit14
```
Output: Contains the password for bandit14
### Commands Used

    - ls - List files in directory

    - ssh -i sshkey.private bandit14@localhost - SSH using private key authentication

    - cat /etc/bandit_pass/bandit14 - Read the password file

### Important Concepts
### SSH Key Authentication

    - Private keys allow passwordless authentication

    - -i flag specifies the identity file (private key)

    - localhost refers to the current machine

    - Key-based authentication is more secure than passwords
