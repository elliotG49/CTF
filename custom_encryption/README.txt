Difficulty: Easy

AUTHOR: NGIRIMANA SCHADRACK

Description
Can you get sense of this code file and write the function that will decode the given encrypted file content.
Find the encrypted file here flag_info and code file might be good to analyze and get the flag.

SOLUTION: 

1. Viewing the 'enc_flag' file, we are greeted by:

a = 95
b = 21
cipher is: [237915, 1850450, 1850450, 158610, 2458455, 2273410, 1744710, 1744710, 1797580, 1110270, 0, 2194105, 
555135, 132175, 1797580, 0, 581570, 2273410, 26435, 1638970, 634440, 713745, 158610, 158610, 449395, 158610, 
687310, 1348185, 845920, 1295315, 687310, 185045, 317220, 449395]

2. After taking a look at the 'custom_encryption.py' file, it was clear that the encryption took place over two stages:

1st: xoring the plaintext with the text_key 'trudeau'
2nd: encoding each character into is ASCII value, then multiplying it by 'key*311'

3. in orderer to decrypt, 'key' needs to be worked out. Thankfully, all the values we need are provided for us.

p = 97
g = 31

4. u, v and key are all created by the 'generator' function, which takes 3 parameters: g, x, p. It does g^x % p.

after performing this for too find the 3 values we are left with:

u = 72
v = 8
key = 85

5. To decrypt, all we have to do is perform the encryption in the opposite order, and therefore a short python script can be created to perform this:

cipher = [237915, 1850450, 1850450, 158610, 2458455, 2273410, 1744710, 1744710, 1797580, 1110270, 0, 2194105, 555135, 132175, 1797580, 0, 581570, 2273410, 26435, 1638970, 634440, 713745, 158610, 158610, 449395, 158610, 687310, 1348185, 845920, 1295315, 687310, 185045, 317220, 449395]

key = 85
text_key = "trudeau"
cipher_text = ""
for value in cipher:
    cipher_text += chr(value // (key * 311))
print(cipher_text)

key_length = len(text_key)
decrypted_text = ""
for i, char in enumerate(cipher_text):
    key_char = text_key[i % key_length]
    decrypted_char = chr(ord(char) ^ ord(key_char))
    decrypted_text += decrypted_char
print(decrypted_text[::-1])

this gives us the flag:

picoCTF{custom_d2cr0pt6d_66778b34}

