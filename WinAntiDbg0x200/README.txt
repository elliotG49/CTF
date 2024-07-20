Difficulty: Medium

AUTHOR: NANDAN DESAI

Description
If you have solved WinAntiDbg0x100, you'll discover something new in this one. Debug the executable and find the flag!
This challenge executable is a Windows console application, and you can start by running it using Command Prompt on Windows.
This executable requires admin privileges. You might want to start Command Prompt or your debugger using the 'Run as administrator' option.

Hints used: 0

SOLUTION:

1. After opening the file up in IDA, I ran the executable again without any modifications, and similair to WinAntiDbg0x100, I recieved the two outputs:

Debugged application message: ### Level 2: Why did the parent process get a promotion at work? Because it had a "fork-tastic" child process that excelled in multitasking!

777B5990: thread has started (tid=16120) 
Debugged application message: ### Oops! The debugger was detected. Try to bypass this check to get the flag!

2. After running the file once with step over instructions, I noticed that at '.text:00981824 test    edx, edx' it went down the route of printing 'a debugger is present'.
Therefore I set a breakpoint at this instruction.

3. The instruction after this was 'jnz     short loc_981832' meaning that to not go down the debugger print path, I would have to change the value of EDX to 0.

4. The next function is a call to 'isDebuggerPresent', this is the same funcntion that was within x100, so using IDA 'zero value' on the eax register we would again traverse to the 'correct' path. 

.text:00981828 call    ds:IsDebuggerPresent
.text:0098182E test    eax, eax
.text:00981830 jz      short loc_981847

5. Once this is done, and the exe is ran to the end , we can retrieve the flag:

Debugged application message: ### Good job! Here's your flag:

Debugged application message: ### ~~~ 
777B5990: thread has started (tid=13576) 
Debugged application message: picoCTF{0x200_debug_f0r_Win_e6b68f6e}
