# Bandit Level 20 → Level 21

## Level Information
- **Level:** 20 → 21
- **Username:** bandit20
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
There is a setuid binary in the homedirectory that makes a connection to localhost on a specified port. It reads a line of text from the connection and compares it to the password of the current level. If correct, it transmits the password for the next level.

## Solution Steps

### 1. Connect to Bandit20
```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
### 2. Understand the Setuid Binary
```bash
./suconnect
```
Output: Shows usage instructions
### 3. Set Up Network Listener in One Terminal
In one SSH session, set up a listener on port 1234 with the current password:
```bash
nc -l -p 1234 < /etc/bandit_pass/bandit20
```
### 4. Connect with suconnect in Another Terminal
In a second SSH session, connect to the listener:
```bash
./suconnect 1234
```
Output: Confirms password match and sends the next password
### Commands Used
- ./suconnect - View binary usage

- nc -l -p 1234 < /etc/bandit_pass/bandit20 - Set up listener with current password

- ./suconnect 1234 - Connect to listener to get next password

## Important Concepts
### Network Communication
- nc -l -p 1234 creates a TCP listener on port 1234

- Input redirection (<) sends file content through the connection

- Localhost communication between processes

### Two Terminal Sessions
- Requires two simultaneous SSH connections

- One acts as server (listener)

- One acts as client (suconnect)

- Demonstrates client-server communication
