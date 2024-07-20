Difficulty:  Easy

Hints used: 0

AUTHOR: JEFFERY JOHN

Description
Why search for the flag when I can make a bookmarklet to print it for me?

SOLUTION:

1. After visiting the website, the first thing I did was to search for the javascript within the HTML code; first pointed out by the name of the challenge and the hint on the website.

2. The website contains this javascript function:

javascript:(function() {
    var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÔÅÐÙí";
    var key = "picoctf";
    var decryptedFlag = "";
    for (var i = 0; i < encryptedFlag.length; i++) {
        decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
    }
    alert(decryptedFlag);
})();

3. On chrome, you can do 'ctrl+shift+j' in order to run javascript code, after pasting in the function, we are given the flag:

picoCTF{p@g3_turn3r_1d1ba7e0}