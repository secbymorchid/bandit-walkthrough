# Bandit Level 16 → Level 17

## Level Information
- **Level:** 16 → 17
- **Username:** bandit16
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. Find which port has a server listening and speaks SSL/TLS.

## Solution Steps

### 1. Connect to Bandit16
```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```
### 2. Scan Ports 31000-32000
```bash
nmap -p 31000-32000 localhost
```
Output: Shows open ports in the range
### 3. Test SSL/TLS Ports
Test each open port with SSL/TLS:
```bash
ncat --ssl localhost 31790
```
Then paste the current level's password and press Enter.
Output: Returns an RSA private key for bandit17
### 4. Save and Use the Private Key
On your local machine:
```bash
# Save the private key to a file
vim key_bandit17

# Set proper permissions
chmod 400 key_bandit17

# Connect using the private key
ssh -i key_bandit17 bandit17@bandit.labs.overthewire.org -p 2220
```
### Commands Used

    - nmap -p 31000-32000 localhost - Scan port range for open ports

    - ncat --ssl localhost 31790 - Connect to SSL/TLS service

    - chmod 400 key_bandit17 - Set secure permissions for private key

    - ssh -i key_bandit17 - SSH using private key authentication

## Important Concepts
### Port Scanning

    - nmap scans for open ports on a target

    - Useful for discovering available services

    - Port ranges help narrow down search space

### SSL/TLS Services

    - Some ports may require SSL/TLS encryption

    - ncat --ssl connects with SSL/TLS support

    - Only one service returns the private key

### SSH Key Authentication

    - Private keys provide secure authentication

    - Must have proper file permissions (600 or 400)

    - Eliminates need for password authentication```
