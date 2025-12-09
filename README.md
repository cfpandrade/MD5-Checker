# File Hash Checker

This script checks the integrity of a file by comparing its hash with an expected hash value. It uses the MD5 algorithm to compute the hash.

## Prerequisites

Before using this script, ensure that you have the following:

- Bash shell environment
- The `md5sum` command-line tool (usually pre-installed on most Unix-like systems)

## Usage

To run the script, execute the following command:
./md5check <file> <hash>

- `<file>`: The path to the file you want to check.
- `<hash>`: The expected MD5 hash value of the file (32 hexadecimal characters).

**Color-coded output:**
- Success messages appear in **green**
- Error messages appear in **red**

The script validates that:
- Both arguments are provided
- The file exists
- The hash is in valid MD5 format (32 hexadecimal characters)

If any validation fails, the script will display an error message and exit with a non-zero status code.

## Example

Here's an example of how to use the script:
```bash
./md5check myfile.txt d41d8cd98f00b204e9800998ecf8427e
```

This command checks if the file `myfile.txt` has an MD5 hash of `d41d8cd98f00b204e9800998ecf8427e`.

**Output when hashes match (displayed in green):**
```
------------
Hashes match
------------
Hash: d41d8cd98f00b204e9800998ecf8427e
```

**Output when hashes don't match (displayed in red):**
```
-------------------
Hashes do not match
-------------------
Expected: d41d8cd98f00b204e9800998ecf8427e
Computed: 5d41402abc4b2a76b9719d911017c592
```

**Error cases (displayed in red):**
```bash
# Invalid hash format
./md5check myfile.txt invalidhash
# Output: Error: Invalid MD5 hash format.

# File doesn't exist
./md5check nonexistent.txt d41d8cd98f00b204e9800998ecf8427e
# Output: The file 'nonexistent.txt' does not exist.
```

## License

This script is released under the MIT License. Feel free to modify and distribute it as needed.