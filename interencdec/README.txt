Difficulty: EASY

Hints used: 0

AUTHOR: NGIRIMANA SCHADRACK

Description
Can you get the real meaning from this file.

SOLUTION: 

1. The contents of enc_flag = 'YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyMHdNakV5TnpVNGZRPT0nCg=='. This is clearly a base64 encoded string. Going to CyberChef and Using the 'FromBase64' Module, we get the following output:

"b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX20wMjEyNzU4fQ=='"

2. This again looks like a base64 encoded string, however, this time it includes a python byte literal prefix.

3. The base64 library in python can be used to decode the string using the following code:

import base64

encoded_str = b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX20wMjEyNzU4fQ=='
decoded_bytes = base64.b64decode(encoded_str)
decoded_str = decoded_bytes.decode('utf-8')
print(decoded_str)

4. This prints an encrypted version of the flag:

wpjvJAM{jhlzhy_k3jy9wa3k_m0212758}

5. However as this string clearly has the same format as a typical flag, a substitution cipher was most likely used. An online ceaser cipher decoder can be used to automatically find the key (only 26 possible options).

picoCTF{caesar_d3cr9pt3d_f0212758}
 
