Difficulty: EASY

Hints used: 1

AUTHOR: NANA AMA ATOMBO-SACKEY & SABINE GISAGARA

Description

-----

SOLUTION:

1. After visiting the allocated website in Burpsuites Chrome Browser, we are greeted by registration page. Entering bogus details into this page will then lead us to a OPT page. 

2. I first thought that the 2FA was valid, however after testing it, it clearly wasnt. Using Burpsuites Proxy to capture the OPT request, my first thought was to brute force the OPT code using the Intruder module, (In hindsight the solution to this problem was much more simple).

3. After this time-expensive process brought saught no goods, I attempted to remove/change certain aspects of the POST req, I removed the cookie, changed it to random values, and then finally removed the OPT variable. Using the repeater to show the response, the flag was able to be obtained.

picoCTF{#0TP_Bypvss_SuCc3$S_b3fa4f1a}