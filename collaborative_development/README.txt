Difficulty: Easy

AUTHOR: JEFFERY JOHN

Description
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

SOLUTION:

1. After unzipping the zip file, my process for starting to find the flag is very similiar to 'collaborative devellopment'; 

grep -r "pico" log/HEAD

This gave the following output:

 grep -r "pico" logs/HEAD

0000000000000000000000000000000000000000 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  commit (initial): init flag printer
5e4b2dae1868abb644627483c78a683286dfe67c 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  checkout: moving from main to feature/part-1
5e4b2dae1868abb644627483c78a683286dfe67c 300cff1bf1f64637dd9ff603d90176e8e8bdeb01 picoCTF <ops@picoctf.com> 1710202077 +0000  commit: add part 1
300cff1bf1f64637dd9ff603d90176e8e8bdeb01 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  checkout: moving from feature/part-1 to main
5e4b2dae1868abb644627483c78a683286dfe67c 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  checkout: moving from main to feature/part-2
5e4b2dae1868abb644627483c78a683286dfe67c 74989a4f650d024929388b6788d2b4c214a07e49 picoCTF <ops@picoctf.com> 1710202077 +0000  commit: add part 2
74989a4f650d024929388b6788d2b4c214a07e49 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  checkout: moving from feature/part-2 to main
5e4b2dae1868abb644627483c78a683286dfe67c 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  checkout: moving from main to feature/part-3
5e4b2dae1868abb644627483c78a683286dfe67c 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be picoCTF <ops@picoctf.com> 1710202077 +0000  commit: add part 3
12c2ae89d8035b7a5aa7cd169dc9e93cc68201be 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000  checkout: moving from feature/part-3 to main

2. The second command used was 'git show 5e4b2dae1868abb644627483c78a683286dfe67c', in order to get details on that particular commit. This gave the followi ng output:

commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer

diff --git a/flag.py b/flag.py
new file mode 100644
index 0000000..77d6cec
--- /dev/null
+++ b/flag.py
@@ -0,0 +1 @@
+print("Printing the flag...")

3. This looks like a part of a larger python file, As there was several hashes within the original output, I did 'git show' on all the other hashes.

commit 300cff1bf1f64637dd9ff603d90176e8e8bdeb01 (feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 1

diff --git a/flag.py b/flag.py
index 77d6cec..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,2 @@
 print("Printing the flag...")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file

------

commit 74989a4f650d024929388b6788d2b4c214a07e49 (feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 2

diff --git a/flag.py b/flag.py
index 77d6cec..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file

----

commit 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be (feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    add part 3

diff --git a/flag.py b/flag.py
index 77d6cec..c312152 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("w0rk_798f9981}")


4. We now have all the parts of the flag.

Flag:

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981}