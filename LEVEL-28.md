#Bandit Level 27 → Level 28


## Level Information
- **Level:** 25 → 26
- **Username:** bandit25
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220


## Level Goal
There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo. The password for the user bandit27-git is the same as for the user bandit27.

Clone the repository and find the password for the next level.

## Solution Steps

### 1. Connect to Bandit27
````bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
````
### 2. Create Temporary Working Directory
````bash
mkdir /tmp/mydir123
cd /tmp/mydir123
````
### 3. Clone Git Repository
````bash
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
````
Password: Use bandit27 password when prompted

### 4. Navigate to Repository
````bash
cd repo
````
### 5. Examine Repository Contents
````bash
ls -la
cat README
````
Output: Shows password in README file

## Important Concepts
### Git Repository Access
- SSH-based git repository

- Repository contains credentials in plain text

- Demonstrates information disclosure in version control

- Shows importance of .gitignore and credential management
