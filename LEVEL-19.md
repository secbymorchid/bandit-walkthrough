# Bandit Level 18 → Level 19

## Level Information
- **Level:** 18 → 19
- **Username:** bandit18
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in a file `readme` in the homedirectory. Unfortunately, someone has modified `.bashrc` to log you out when you log in with SSH.

## Solution Steps

### 1. Execute Remote Command Without Interactive Shell
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```
Output: Contains the password for bandit19
### Commands Used

    - ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme" / Execute remote command directly without interactive shell

## Important Concepts
### Non-Interactive SSH

    - Running commands directly via SSH avoids the interactive shell

    - Prevents .bashrc from executing and logging you out

    - Useful for remote administration and automation

    - Command is executed and connection closes immediately

### .bashrc Modification

    - .bashrc runs when an interactive shell starts

    - Malicious modifications can disrupt normal login

    - Bypass by running commands non-interactively

    - Security consideration: be careful with shell configuration files
