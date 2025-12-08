# Bandit Level 26 → Level 27


## Level Information
- **Level:** 26 → 27

- **Username:** bandit26

- **Host:** bandit.labs.overthewire.org

- **Port:** 2220

## Level Goal
Good job getting a shell! Now find the password for bandit27.

## Solution Steps
#### 1. From Previous Level Shell
We should already have a bash shell from the previous exploit. If not, follow Level 25→26 steps first.

### 2. Check Available Files
```bash
ls -la
```
Output: Shows bandit27-do executable file

### 3. Analyze the Setuid Executable
```bash
file bandit27-do
```
Output: Shows setuid ELF executable

### 4. Exploit Setuid Privileges
```bash
./bandit27-do whoami
```
Output: Shows bandit27 (runs command as bandit27)

### 5. Read Bandit27 Password
```bash
./bandit27-do cat /etc/bandit_pass/bandit27
````
Output: Contains the password for bandit27

## Important Concepts
### Setuid Exploitation
- bandit27-do has setuid bit set

- Executes commands with bandit27 privileges

- Allows reading bandit27's password file

- Demonstrates privilege escalation via misconfigured permissions
