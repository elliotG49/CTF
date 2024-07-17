Difficulty: EASY

Hints used: 0

AUTHOR: SYREAL

Description
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

SOLUTION:

1. When downloading the file, the official file suffix is '.pdf'. When opening this file with chrome, half the flag can be retrieved: '1n_pn9_&_pdf_53b741d6}'.

2. Clearly there is more to this file than meets the eye, using 'strings', '�PNG' can be seen, possibly indicating that this file is also an image file. 

3. When opening this file with an image application, such as MS Paint, the first part of the flag can be seen in the image: 

'picoCTF{f1u3n7_'
