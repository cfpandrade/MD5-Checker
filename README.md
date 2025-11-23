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
- `<hash>`: The expected hash value of the file.

If the file and hash arguments are not provided or if the file does not exist, the script will display an error message and exit with a non-zero status code.

## Example

Here's an example of how to use the script:
./md5check myfile.txt d41d8cd98f00b204e9800998ecf8427e

This command checks if the file `myfile.txt` has an MD5 hash of `d41d8cd98f00b204e9800998ecf8427e`. If the computed hash matches the expected hash, it displays the message "Hashes match." Otherwise, it displays the message "Hashes do not match."

Please note that the expected hash should be the MD5 hash of the file, represented as a 32-character hexadecimal string.

## License

This script is released under the MIT License. Feel free to modify and distribute it as needed.