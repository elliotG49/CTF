Diffuculty: EASY

Hints used: 0

AUTHOR: JEFFERY JOHN

Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.

SOLUTION:

1. Use 'sha256sum' to hash all the files in the directory: 'find . -type f -exec sha256sum {} \; > hash.txt'
2. Use grep to find the hash of the file: 'cat hash.txt | grep "example-hash"
3. Decrypt the file and find the flag!
