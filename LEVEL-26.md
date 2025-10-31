# Bandit Level 25 → Level 26

## Level Information
- **Level:** 25 → 26
- **Username:** bandit25
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

## Solution Steps

### 1. Connect to Bandit25
```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
```
### 2. Check Available Files
```bash
ls -la
```
Output: Shows bandit26.sshkey file
### 3. Analyze Bandit26's Shell Configuration
```bash
cat /etc/passwd | grep bandit26
```
Output: Shows bandit26 uses custom shell /usr/bin/showtext
### 4. Examine the Custom Shell
```bash
cat /usr/bin/showtext
```
Output: Shows script that uses more command to display text
### 5. Prepare Terminal for Exploit
!! CRITICAL STEP: Shrink your terminal window to about 5-6 lines in height
### 6. Login to Bandit26
```bash
ssh -i bandit26.sshkey bandit26@localhost -p 2220
```
### 7. Exploit more/vi Integration
When more pauses due to small terminal size:

Press v to launch vi editor

In vi command mode, type:
```bash
:set shell=/bin/bash
```
Press Enter, then type:
```bash
:shell
```
Press Enter
### 8. Retrieve Bandit26 Password
```bash
cat /etc/bandit_pass/bandit26
```
Output: Contains the password for bandit26
### Commands Used
- ssh bandit25@bandit.labs.overthewire.org -p 2220 - Connect to bandit25

- ls -la - List files including SSH key

- cat /etc/passwd | grep bandit26 - Find bandit26's custom shell

- cat /usr/bin/showtext - Examine restricted shell script

- ssh -i bandit26.sshkey bandit26@localhost -p 2220 - SSH using keyfile

- :set shell=/bin/bash - Vi command to change shell

- :shell - Vi command to spawn shell

- cat /etc/bandit_pass/bandit26 - Retrieve password

## Important Concepts
### Restricted Shell Bypass
- Bandit26 uses custom shell instead of /bin/bash

- Shell executes more ~/text.txt then exits

- Small terminal forces more to pause and wait for input

### more/vi Feature Exploitation
- more can launch vi editor when paused

- vi can spawn system shells despite restricted environment

- Creates escape chain from restricted execution
