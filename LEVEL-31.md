# Bandit Level 30 → Level 31
## Level Information
- **Level:** 30 → 31
- **Username:** bandit30
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo. The password for the user bandit30-git is the same as for the user bandit30.

Clone the repository and find the password for the next level.

## Solution Steps
### 1. Connect to Bandit30
````bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
````
### 2. Create Temporary Directory
````bash
mkdir /tmp/mydir012
cd /tmp/mydir012
````
 Clone Git Repository
````bash
git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
````
Password: Use bandit30 password when prompted

### 4. Check Git Tags
````bash
cd repo
git tag
````
Output: Shows a tag name

### 5. Examine Tag Contents
````bash
git show secret
````
Output: Reveals password stored in tag

## Important Concepts
### Git Tag Storage
- Secrets stored in git tags

- Tags often overlooked in security audits

- Alternative storage location for sensitive data

- Shows comprehensive git security assessment needed
