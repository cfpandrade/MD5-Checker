# File Hash Checker

This script checks the integrity of a file by comparing its hash with an expected hash value. It uses the MD5 algorithm to compute the hash and provides color-coded output for easy visual verification.

## Prerequisites

Before using this script, ensure that you have the following:

- Bash shell environment
- The `md5sum` command-line tool (usually pre-installed on most Unix-like systems)
- Terminal with ANSI color support (most modern terminals)

## Features

- **Color-coded output** for instant visual feedback:
  - 🟢 **Green**: Hash verification successful (files match)
  - 🔴 **Red**: Hash verification failed or errors occurred
- **Hash format validation**: Ensures MD5 hash is exactly 32 hexadecimal characters
- **Detailed error messages**: Shows both expected and computed hashes when they don't match
- **Input validation**: Checks for file existence and proper arguments

## Usage

To run the script, execute the following command:
./md5check <file> <hash>

- `<file>`: The path to the file you want to check.
- `<hash>`: The expected MD5 hash value of the file (32 hexadecimal characters).

The script performs the following validations:
- Both arguments are provided
- The file exists
- The hash is in valid MD5 format (32 hexadecimal characters)

If any validation fails, the script will display an error message and exit with a non-zero status code.

## Examples

### Successful Hash Verification

When the file hash matches the expected value, the output is displayed in **green**:

```bash
./md5check myfile.txt d41d8cd98f00b204e9800998ecf8427e
```

**Output:**
```
------------
Hashes match
------------
Hash: d41d8cd98f00b204e9800998ecf8427e
```
*(All text displayed in green indicating success)*

### Failed Hash Verification

When the computed hash doesn't match the expected value, the output is displayed in **red** with both hashes shown:

```bash
./md5check myfile.txt d41d8cd98f00b204e9800998ecf8427e
```

**Output:**
```
-------------------
Hashes do not match
-------------------
Expected: d41d8cd98f00b204e9800998ecf8427e
Computed: 5d41402abc4b2a76b9719d911017c592
```
*(All text displayed in red indicating failure)*

### Error Cases

All error messages are displayed in **red**:

**Invalid hash format:**
```bash
./md5check myfile.txt invalidhash
```
**Output:** `Error: Invalid MD5 hash format.` *(in red)*

**File doesn't exist:**
```bash
./md5check nonexistent.txt d41d8cd98f00b204e9800998ecf8427e
```
**Output:** `The file 'nonexistent.txt' does not exist.` *(in red)*

**Missing arguments:**
```bash
./md5check myfile.txt
```
**Output:** `Missing file or hash in the command.` *(in red)*

## License

This script is released under the MIT License. Feel free to modify and distribute it as needed.