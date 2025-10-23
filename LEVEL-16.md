# Bandit Level 15 → Level 16

## Level Information
- **Level:** 15 → 16
- **Username:** bandit15
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

## Solution Steps

### 1. Connect to Bandit15
```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
### 2. Submit Current Password via SSL/TLS
```bash
openssl s_client -connect localhost:30001
```
Then paste the current level's password and press Enter.

Output: Contains the password for bandit16
### Commands Used

    - openssl s_client -connect localhost:30001 - Connect to localhost on port 30001 using SSL/TLS

## Important Concepts
### OpenSSL s_client

    - s_client is an SSL/TLS client tool

    - Used to connect to SSL/TLS encrypted services

    - -connect specifies the host and port to connect to

    - Handles SSL certificate verification and encryption

### SSL/TLS Encryption

    - Provides secure encrypted communication

    - Uses certificates for server authentication

    - Port 30001 runs an SSL/TLS encrypted service

    - Self-signed certificates may show verification warnings
