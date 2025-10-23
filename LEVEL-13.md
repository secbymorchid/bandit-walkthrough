# Bandit Level 12 → Level 13

## Level Information
- **Level:** 12 → 13
- **Username:** bandit12
- **Host:** bandit.labs.overthewire.org
- **Port:** 2220

## Level Goal
The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed.

## Solution Steps

### 1. Connect to Bandit12
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```
### 2. Create a Temporary Working Directory
```bash
mktemp -d
```
Output: /tmp/tmp.random_name
#### 3. Copy and Navigate to Working Directory
```bash
cp data.txt /tmp/tmp.random_name/
cd /tmp/tmp.random_name
```
### 4. Convert Hexdump Back to Binary
```bash
xxd data.txt > data.bin
```
### 5. Identify and Extract Compression Layers
Repeatedly check file type and extract:
First layer - gzip:
```bash
file data.bin
mv data.bin data.gz
gzip -d data.gz
```
Second layer - bzip2:
```bash
file data
mv data data.bz2
bzip2 -d data.bz2
```
Third layer - gzip:
```bash
file data
mv data data.gz
gzip -d data.gz
``` 
Fourth layer - tar:
```bash
file data
mv data data.tar
tar -xf data.tar
```
Fifth layer - tar:
```bash
file data5.bin
mv data5.bin data.tar
tar -xf data.tar
```
Sixth layer - bzip2:
```bash
file data6.bin
mv data6.bin data.bz2
bzip2 -d data.bz2
```
Seventh layer - tar:
```bash
file data
mv data data.tar
tar -xf data.tar
```
Eighth layer - gzip:
```bash
file data8.bin
mv data8.bin data.gz
gzip -d data.gz
```
### 6. Read the Final Password
```bash
cat data
```
Output: Contains the password for bandit13
## Commands Used

    - mktemp -d - Create secure temporary directory

    - xxd -r - Reverse hexdump to binary

    - file - Identify file type

    - gzip -d - Decompress gzip files

    - bzip2 -d - Decompress bzip2 files

    - tar -xf - Extract tar archives
