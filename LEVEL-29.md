# Bandit Level 28 → Level 29

## Level Information
- **Level:** 28 → 29
- **Username:** bandit28
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo. The password for the user bandit28-git is the same as for the user bandit28.

Clone the repository and find the password for the next level.

## Solution Steps
### 1. Connect to Bandit28
```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
````
### 2. Create Temporary Directory
````bash
mkdir /tmp/mydir456
cd /tmp/mydir456
````
### 3. Clone Git Repository
```bash
git clone ssh://bandit28-git@localhost/home/bandit28-git/repo
````
Password: Use bandit28 password when prompted

### 4. Check Git History
````bash
cd repo
git log
````
Output: Shows commit history

### 5. Examine Previous Commit
````bash
git show <commit-hash-from-log>
````
Output: Reveals password that was removed in latest commit

## Important Concepts
### Git History Analysis
- Credentials removed in recent commit

- Previous commits still contain sensitive data

- Demonstrates why git filter-branch or BFG is needed to truly remove secrets

- Shows importance of auditing git history
