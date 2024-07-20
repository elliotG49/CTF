Difficulty: Easy

AUTHOR: MUBARAK MIKAIL

Description
How about some hide and seek?

Hints used: 0

SOLUTION:

1. After extracting 'ukn_reality.jpg', the first thing I did was view the file in a image editor, however the image did not reveal anything.

2. My first thought was that this was a sort of steganography hidden data flag find, so using steghide, one of the most known tools, I attempted to extract hidden data:

This gave me the following file:


cat flag:

'The flag is not here maybe think in simpler terms. Data that explains data.'

3. Thinking simpler, I assumed it must be in the meta-data of the file, I attempted to perform strings on the file, but that gave me nothing.

4. exiftool is a common command line tool for reading metadata of common file extension. The output of performing it on this file was:

ExifTool Version Number         : 12.76
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 20:05:55-04:00
File Access Date/Time           : 2024:07:19 16:32:10-04:00
File Inode Change Date/Time     : 2024:07:19 16:31:09-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4

5. The 'Attribution URL' gives an base64 value, after decdding it using CyberChef, the flag can be found:

flag:

picoCTF{ME74D47A_HIDD3N_6a9f5ac4}
