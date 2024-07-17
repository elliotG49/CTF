Difficulty: EASY

Hints used: 0

AUTHOR: ABRXS, PR1OR1TYQ

Description
Can you control your overflow?

SOLUTION: 

1. Looking at the source-code, a strcmp is called; where if the variable 'safe_var' == 'pico', then the flag will be shown
2. When running the exe, two addresses are given to us; the location of 'input_data' and 'safe_var'. These addresses are 32 bytes apart; meaning that any input greater that 32 bytes will overwrite 'safe_var' due to a lack of input validation. 
3. input = 32bytes of data + 'pico'.

ALTERNATE:

1. If the memory addresses were not shown or the difference could not be worked out, an input of easily recognisable text could be used; eg the alphabet, could be used to work out the offset. 

ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEF
