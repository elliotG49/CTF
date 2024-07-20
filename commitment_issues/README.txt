Difficulty: Easy

AUTHOR: JEFFERY JOHN

Description
I accidentally wrote the flag down. Good thing I deleted it!

SOLUTION: 

1. After unzipping the zip file, the first thing to do was a recursive grep for the word pico "pico". This would search the 
word pico for all files within my directory. This outputted the following data:

.git/logs/HEAD:0000000000000000000000000000000000000000 b562f0b425907789d11d2fe2793e67592dc6be93 picoCTF <ops@picoctf.com> 1710201983 +0000   commit (initial): create flag
.git/logs/HEAD:b562f0b425907789d11d2fe2793e67592dc6be93 42942c9c605b30100f5d859ef6e172027447c0db picoCTF <ops@picoctf.com> 1710201983 +0000   commit: remove sensitive info
.git/logs/refs/heads/master:0000000000000000000000000000000000000000 b562f0b425907789d11d2fe2793e67592dc6be93 picoCTF <ops@picoctf.com> 1710201983 +0000      commit (initial): create flag
.git/logs/refs/heads/master:b562f0b425907789d11d2fe2793e67592dc6be93 42942c9c605b30100f5d859ef6e172027447c0db picoCTF <ops@picoctf.com> 1710201983 +0000      commit: remove sensitive info

2. This shows that the flag was created and then deleted.

3. As this is a cloned repo, its possible to use git commands specifically for this repo. Taking the hash from the 'create flag' 
commit, the command 'git show b562f0b425907789d11d2fe2793e67592dc6be93' will show the differences introduced by the git commit.

The output of this was:

commit b562f0b425907789d11d2fe2793e67592dc6be93
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    create flag

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..0e0fefc
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_c785c319}

Flag:

picoCTF{s@n1t1z3_c785c319}