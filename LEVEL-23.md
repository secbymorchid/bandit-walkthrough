# Bandit Level 22 → Level 23

## Level Information
- **Level:** 22 → 23
- **Username:** bandit22
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.

## Solution Steps

### 1. Connect to Bandit22
```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```
### 2. Check Cron Jobs Configuration
``` bash
cd /etc/cron.d/
ls
```
Output: Shows various cron job configuration files
### 3. Examine the Bandit23 Cron Job
```bash
cat cronjob_bandit23
```
Output: Shows the cron schedule and script path
### 4. Read and Analyze the Cron Script
```bash
cat /usr/bin/cronjob_bandit23.sh
```
Output: Shows a script that generates a filename using MD5 hash
### 5. Calculate the Target Filename
```bash
myname=bandit23
echo I am user $myname | md5sum | cut -d ' ' -f 1
```
Output: You'll find the name of the targeted filename
### 6. Read the Password from Calculated File
```bash
cat /tmp/[calculated_filename]
```
Output: Contains the password for bandit23
### Commands Used
- cd /etc/cron.d/ - Navigate to cron directory

- ls - List cron job files

- cat cronjob_bandit23 - View bandit23 cron job configuration

- cat /usr/bin/cronjob_bandit23.sh - Read and analyze the cron script

- echo I am user bandit23 | md5sum | cut -d ' ' -f 1 - Calculate the target filename

- cat /tmp/[calculated_filename] - Read the password file

## Important Concepts
### Dynamic File Naming
- Script uses MD5 hash to generate unique filenames

- whoami returns the executing user (bandit23 when run by cron)

- MD5 creates consistent hash from a specific string pattern

### Script Analysis
- The cron script generates a filename based on an MD5 hash of a string containing the username, then copies the password to that file.
