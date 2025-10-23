# Bandit Level 14 → Level 15

## Level Information
- **Level:** 14 → 15
- **Username:** bandit14
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Solution Steps

### 1. Connect to Bandit14
```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
```
### 2. Submit Current Password to Localhost Port 30000
```bash
nc localhost 30000
```
Then paste the current level's password and press Enter.
Output: Contains the password for bandit15
### Commands Used

    - nc localhost 30000 - Connect to localhost on port 30000 using netcat

## Important Concepts
### Netcat (nc)

    - nc is a networking utility for reading from and writing to network connections

    - Used to connect to services on specific ports

    - localhost refers to the current machine

    - Port 30000 is where the password submission service is running
