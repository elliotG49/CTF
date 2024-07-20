Difficulty: Medium

AUTHOR: NANDAN DESAI

Description
This challenge will introduce you to 'Anti-Debugging.' Malware developers don't like it when you attempt to debug their executable files because debugging these files reveals many of their secrets! That's why, they include a lot of code logic specifically designed to interfere with your debugging process.
Now that you've understood the context, go ahead and debug this Windows executable!
This challenge binary file is a Windows console application and you can start with running it using cmd on Windows.

Hints used: 0

SOLUTION:

1. After Opening up this file with IDA, I first ran the exe without any modifications, however it printed '### Oops! The debugger was detected'
This meant that there was a function that was detecting if I was in a debugger

2. Setting a breakpoint early in the execution, and stepping each instruction after, I was able to find the location of the function call:

.text:00C615FC call    ds:IsDebuggerPresent
.text:00C61602 test    eax, eax
.text:00C61604 jz      short loc_C6161B

3. My first idea was to change the jz function to jnz (the opposite) in order to traverse the 'correct' way, this is also prefferable as it does not 
change/overwrite any data (instructions are the same size (74 & 75)). However, the exe was not compiling correctly, anytime the changes where made within'
 IDA, it would not be correct within runtime. (in hindsight this could be resolved using HxD editior instead of IDA's internal hex editor and working out offsets)

4. Instead of this, IDA allows you to change the contents of registers at runtime; therefore, breakpointed at instruction call 'test' I changed eax to 0.

5. After letting the exe run to the end, the flag was given to me:

Debugged application message: ### Good job! Here's your flag:

Debugged application message: ### ~~~ 
Debugged application message: picoCTF{d3bug_f0r_th3_Win_0x100_e4a066b1}
Debugged application message: