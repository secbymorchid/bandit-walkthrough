# Bandit Level 29 → Level 30

## Level Information
- **Level:** 29 → 30
- **Username:** bandit29
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo. The password for the user bandit29-git is the same as for the user bandit29.

Clone the repository and find the password for the next level.

## Solution Steps
### 1. Connect to Bandit29
````bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
````
### 2. Create Temporary Directory
````bash
mkdir /tmp/mydir789
cd /tmp/mydir789
````
### 3. Clone Git Repository
````bash
git clone ssh://bandit29-git@localhost/home/bandit29-git/repo
````
Password: Use bandit29 password when prompted
### 4. Check Git Branches
````bash
cd repo
git branch -a
````
Output: Shows multiple branches including dev

### 5. Switch to Development Branch
````bash
git checkout dev
````
### 6. Examine Branch Contents
````bash
cat README
````
Output: Shows password in dev branch README

## Important Concepts
### Git Branching Security
- Sensitive data in non-main branches

- Developers often store secrets in feature branches

Shows need for branch protection rules

Demonstrates horizontal privilege escalation via branch access
