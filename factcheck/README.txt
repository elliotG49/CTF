Difficulty: Medium

AUTHOR: JUNIAS BONOU

Description
This binary is putting together some important piece of information... Can you uncover that information?

1. Performing strings on the bin file gives us the first part of the flag:

picoCTF{wELF_d0N3_mate_

2. When trying to execute the file via command line, the file returns no output, even when supplying parameters still no output is given. 
I attempted to look at the file with gdb (-q for debugging) however no debugging was given and therefor it could not be analaysed

3. Opening the executable with Ghidra, we can take a look at the 'main' function. Notably a basic string function kept being called, which took a predefined character and allocated it to a new variable name, eg:

/* try { // try from 0010130a to 0010130e has its CatchHandler @ 00101996 */
  std::__cxx11::basic_string<>::basic_string((char *)char_9,(allocator *)&DAT_0010201d);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();

4. DAT_* is the location of the pre-def character, and char_9 was the new variable it was assigned to. To make it easier, I made sure to change (from local_*) the variale name it was assigned to included the character it contained.

local_288 = char_9
local_208 = char_5
local_1e8 = char_a
local_1c8 = char_3
local_1a8 = char_c
local_188 = char_9
local_168 = char_a
local_148 = char_e
local_128 = char_5
local_108 = char_d
local_e8 =  char_b
local_c8 = char_9
local_a8 = char_6
local_88 = char_b
local_68 = char_3
local_48 = char_8

std::__cxx11::basic_string<>::basic_string
            ((char *)flag_first_half,(allocator *)"picoCTF{wELF_d0N3_mate_");
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 0010130a to 0010130e has its CatchHandler @ 00101996 */
  std::__cxx11::basic_string<>::basic_string((char *)char_9,(allocator *)&DAT_0010201d);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101345 to 00101349 has its CatchHandler @ 001019b1 */
  std::__cxx11::basic_string<>::basic_string((char *)char_5,(allocator *)&DAT_0010201f);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101380 to 00101384 has its CatchHandler @ 001019cc */
  std::__cxx11::basic_string<>::basic_string((char *)char_a,(allocator *)&DAT_00102021);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 001013bb to 001013bf has its CatchHandler @ 001019e7 */
  std::__cxx11::basic_string<>::basic_string((char *)char_3,(allocator *)&DAT_00102023);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 001013f6 to 001013fa has its CatchHandler @ 00101a02 */
  std::__cxx11::basic_string<>::basic_string((char *)char_c,(allocator *)&DAT_00102025);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101431 to 00101435 has its CatchHandler @ 00101a1d */
  std::__cxx11::basic_string<>::basic_string((char *)char_9&,(allocator *)&DAT_0010201d);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 0010146c to 00101470 has its CatchHandler @ 00101a38 */
  std::__cxx11::basic_string<>::basic_string((char *)char_a&,(allocator *)&DAT_00102021);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 001014a7 to 001014ab has its CatchHandler @ 00101a53 */
  std::__cxx11::basic_string<>::basic_string((char *)char_e,(allocator *)&DAT_00102027);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 001014e2 to 001014e6 has its CatchHandler @ 00101a6e */
  std::__cxx11::basic_string<>::basic_string((char *)char_5&,(allocator *)&DAT_0010201f);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 0010151d to 00101521 has its CatchHandler @ 00101a89 */
  std::__cxx11::basic_string<>::basic_string((char *)char_d,(allocator *)&DAT_00102029);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101558 to 0010155c has its CatchHandler @ 00101aa4 */
  std::__cxx11::basic_string<>::basic_string((char *)char_b,(allocator *)&DAT_0010202b);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101593 to 00101597 has its CatchHandler @ 00101abf */
  std::__cxx11::basic_string<>::basic_string((char *)char_9*,(allocator *)&DAT_0010201d);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 001015ce to 001015d2 has its CatchHandler @ 00101ada */
  std::__cxx11::basic_string<>::basic_string((char *)char_6,(allocator *)&DAT_0010202d);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101606 to 0010160a has its CatchHandler @ 00101af5 */
  std::__cxx11::basic_string<>::basic_string((char *)char_b*,(allocator *)&DAT_0010202b);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 0010163e to 00101642 has its CatchHandler @ 00101b0d */
  std::__cxx11::basic_string<>::basic_string((char *)char_3*,(allocator *)&DAT_00102023);
  std::allocator<char>::~allocator(&local_249);
  std::allocator<char>::allocator();
                    /* try { // try from 00101676 to 0010167a has its CatchHandler @ 00101b25 */
  std::__cxx11::basic_string<>::basic_string((char *)char_8,(allocator *)&DAT_0010202f);
  std::allocator<char>::~allocator(&local_249);
                    /* try { // try from 00101699 to 0010185f has its CatchHandler @ 00101b3d */

5. After the assigning of variables, the main function appended certain variables depending on certain if statements.

The first, pcVar2, which is assigned to char_5, is checked if it is larger than 'B', which using an ASCII table; 5 = 53, B = 66, b is bigger, and therefor char_9 is appended to the flag.

So far our flag = picoCTF{wELF_d0N3_mate_9

6. Doing this for the rest of the if statements appends

  pcVar2 = (char *)std::__cxx11::basic_string<>::operator[]((ulong)char_5);
  if (*pcVar2 < 'B') {
    std::__cxx11::basic_string<>::operator+=(flag_first_half,char_9*);
  }
  pcVar2 = (char *)std::__cxx11::basic_string<>::operator[]((ulong)char_6);
  if (*pcVar2 != 'A') {
    std::__cxx11::basic_string<>::operator+=(flag_first_half,char_3*);
  }
  pcVar2 = (char *)std::__cxx11::basic_string<>::operator[]((ulong)char_3);
  cVar1 = *pcVar2;
  pcVar2 = (char *)std::__cxx11::basic_string<>::operator[]((ulong)char_e);
  if ((int)cVar1 - (int)*pcVar2 == 3) {
    std::__cxx11::basic_string<>::operator+=(flag_first_half,char_3);
  }
  std::__cxx11::basic_string<>::operator+=(flag_first_half,char_a);
  std::__cxx11::basic_string<>::operator+=(flag_first_half,char_9&);
  pcVar2 = (char *)std::__cxx11::basic_string<>::operator[]((ulong)char_a&);
  if (*pcVar2 == 'G') {
    std::__cxx11::basic_string<>::operator+=(flag_first_half,char_a&);
  }
  std::__cxx11::basic_string<>::operator+=(flag_first_half,char_c);
  std::__cxx11::basic_string<>::operator+=(flag_first_half,char_b*);
  std::__cxx11::basic_string<>::operator+=(flag_first_half,char_9);
  std::__cxx11::basic_string<>::operator+=(flag_first_half,char_5&);
  std::__cxx11::basic_string<>::operator+=(flag_first_half,'}')

We get the flag:

picoCTF{wELF_d0N3_mate_93a9cb95}
