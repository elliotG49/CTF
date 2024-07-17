Difficulty: EASY

Hints used: 0

AUTHOR: JEFFERY JOHN

Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

SOLUTION:

1. Binary Search = Divide search space by 2, then compare the element with the middle of the search space
2. For every entry into guessing script, perform (highest guess possible + lowest guess possible) / 2
3. Enter that number in every time, and you will always find the correct number by the last guess.

Formula for time complexity of binary search:

T(n) = log^2n
