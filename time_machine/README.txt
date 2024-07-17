Difficulty: EASY

Hints used: 0

Description
What was I last working on? I remember writing a note to help me remember...

SOLUTION:

1. When unzipping the file and performing a simple 'ls' and subsquently reading 'message.txt', it states:

'This is what I was working on, but I'd need to look at my commit history to know why...'
 
2. After performing 'ls -al' to find hidden files in the dir, '.git' shows up.

3. Using 'grep', which matches searches and patterns in a file, the command: 'grep -r "pico"' was used, and returned the the correct flag.
