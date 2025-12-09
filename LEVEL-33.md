# Bandit Level 32 → Level 33
## Level Information
- **Level:** 32 → 33
- **Username:** bandit32
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
After all this git stuff its time for another escape. Good luck!

## Solution Steps
### 1. Connect to Bandit32
````bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
````
### 2. Understand the UPPERCASE Shell
Upon login, you're in a shell that converts all input to uppercase

````bash
$ ls
# Converts to: LS (command not found)
````
### 3. Exploit Shell Variable Expansion
````bash
$0
````
This executes the current shell program (bypasses uppercase conversion)

### 4. Get Normal Shell
```èbash
$0
# Then once in new shell:
/bin/bash
````
### 5. Retrieve Bandit33 Password
````bash
cat /etc/bandit_pass/bandit33
````
##Important Concepts
- Restricted Shell Escape
- UPPERCASE shell transforms all input

- $0 references the current shell/program name

- Environment variables bypass input transformation

- Demonstrates shell meta-character exploitation
