Difficulty: EASY

Hints used: 0

AUTHOR: NANA AMA ATOMBO-SACKEY

Description
Know of little and big endian?

SOLUTION:

1. When connecting to the server, we are greeted by a 5 letter random string of characters, in my case this was: 'uhkcb'.

2. The program first asks you to input the string in 'littl-endian', which means the putting the least significant byte first. Using a ASCII to hexedical converter, we get obtain the hex in Big Endian, which is usually defualt.

'75686B6362'

3. To turn this into little endian, we split this into bytes, and then reverse the order. The output of this is:

'62636B6875'

4. After entering both of these values, we can obtain the flag:

picoCTF{3ndi4n_sw4p_su33ess_cfe38ef0}