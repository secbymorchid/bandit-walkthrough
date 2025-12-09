# Bandit Level 31 → Level 32
## Level Information
- **Level:** 31 → 32
- **Username:** bandit31
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo. The password for the user bandit31-git is the same as for the user bandit31.

Clone the repository and find the password for the next level.

## Solution Steps
### 1. Connect to Bandit31
````bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
````
### 2. Create Temporary Directory
````bash
mkdir /tmp/mydir345
cd /tmp/mydir345
````
### 3. Clone Git Repository
````bash
git clone ssh://bandit31-git@localhost/home/bandit31-git/repo
````
Password: Use bandit31 password when prompted

### 4. Check .gitignore
````bash
cd repo
cat .gitignore
````
Output: Shows *.txt files are ignored

### 5. Create Required File
````bash
echo "May I come in?" > key.txt
 ````
### 6. Add, Commit, and Push
 ````bash
git add -f key.txt
git commit -m "Adding key.txt"
git push origin master
````
Password: Use bandit31 password when prompted

### 7. Check Output for Password
Output from git push contains the password for bandit32

## Important Concepts
### Gitignore Bypass
- .gitignore configured to ignore certain files

- git add -f forces addition of ignored files

Push triggers remote hook that reveals password

Shows server-side git hooks and their security implications
