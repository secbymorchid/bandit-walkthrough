# Bandit Level 21 → Level 22

## Level Information
- **Level:** 21 → 22
- **Username:** bandit21
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.

## Solution Steps

### 1. Connect to Bandit21
```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```
### 2.2. Check Cron Jobs Configuration
```bash
cd /etc/cron.d/
ls
``` 
Output: Shows various cron job files
### 3. Examine the Bandit22 Cron Job
```bash
cat cronjob_bandit22
``` 
Output: Shows the cron job schedule and script location
### 4. Read the Cron Script
```bash
cat /usr/bin/cronjob_bandit22.sh
```
Output: Shows the script copies bandit22 password to a temporary file
### 5. Read the Password from Temporary File
```bash
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
``` 
Output: Contains the password for bandit22
### Commands Used
- cd /etc/cron.d/ - Navigate to cron directory

- ls - List cron job files

- cat cronjob_bandit22 - View bandit22 cron job configuration

- cat /usr/bin/cronjob_bandit22.sh - Read the cron script

- cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv - Read the password file

## Important Concepts
### Cron System
- Cron is a time-based job scheduler in Unix-like systems

- /etc/cron.d/ contains system cron job configurations

- @reboot runs at system startup

- * * * * * runs every minute

### Cron Job Analysis
- Cron jobs can run scripts with specific user privileges

- Scripts may expose sensitive information through file operations

- Understanding cron configurations helps identify security issues

  
