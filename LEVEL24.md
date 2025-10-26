# Bandit Level 23 → Level 24

## Level Information
- **Level:** 23 → 24
- **Username:** bandit23
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.

## Solution Steps

### 1. Connect to Bandit23
```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220
```
### 2. Check Cron Jobs Configuration
```bash
cat /etc/cron.d/cronjob_bandit24
```
Output: Shows the cron schedule and script path
### 3. Read and Analyze the Cron Script
```bash
cat /usr/bin/cronjob_bandit24.sh
```
Output: Shows a script that executes all scripts in /var/spool/bandit24/foo directory
### 4. Create a Working Directory
```bash
mkdir /tmp/mydir
cd /tmp/mydir
```
### 5. Create a Script to Read the Password
```bash
vim sol.sh
```
Add the following content:
```bash
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/mydir/pass
```
### 6. Make Script Executable and Create Output File
```bash
chmod 777 sol.sh
touch pass
chmod 777 pass
```
### 7. Copy Script to Cron Directory
```bash
cp sol.sh /var/spool/bandit24/foo/
```
### 8. Wait for Cron Execution and Check Result
```bash
cat pass
```
Output: Contains the password for bandit24
### Commands Used
- cat /etc/cron.d/cronjob_bandit24 - View cron job configuration

- cat /usr/bin/cronjob_bandit24.sh - Analyze the cron script

- mkdir /tmp/mydir - Create working directory

- vim sol.sh - Create script to read password

- chmod 777 sol.sh - Make script executable

- cp sol.sh /var/spool/bandit24/foo/ - Copy script to cron directory

- cat pass - Read the obtained password

## Important Concepts
### Cron Script Execution
- Cron runs scripts from /var/spool/bandit24/foo/ directory

- Scripts are executed and then deleted

- Scripts run with bandit24 privileges

### Shell Script Creation
- Create a script that reads the bandit24 password

- Output the password to a file in your accessible directory

- Script must be executable and placed in the correct location

### File Permissions
- Ensure both script and output file have proper permissions

- Script needs execute permissions

- Output file needs write permissions













