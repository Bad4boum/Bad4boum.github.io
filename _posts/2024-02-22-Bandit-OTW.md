---
title: "OverTheWire - Bandit"
date: 2024-02-22 12:00:00 +/-0530
categories: [OverTheWire]
tags: [OTW]     # TAG names should always be lowercase
---

![OverTheWire](https://overthewire.org/img/domokitten.png)


## :scroll: Description 

> The Bandit wargame is aimed at absolute beginners. It will teach the basics needed to be able to play other wargames. **If you notice something essential is missing or have ideas for new levels, please let us know!**

:point_right: Play [here](https://overthewire.org/wargames/bandit/) ! :point_left:



<br>
  

## :page_with_curl: Summary :  

- Level 0-10 : &nbsp; [Level 0](#star2-level-0) | [Level 1](#star2-level-1) | [Level 2](#star2-level-2) | [Level 3](#star2-level-3) | [Level 4](#star2-level-4) | [Level 5](#star2-level-5) | [Level 6](#star2-level-6) | [Level 7](#star2-level-7) | [Level 8](#star2-level-8) | [Level 9](#star2-level-9) | [Level 10](#star2-level-10)

<br>
  
- Level 11-20 : [Level 11](#star2-star2-level-11) | [Level 12](#star2-star2-level-12) | [Level 13](#star2-star2-level-13) | [Level 14](#star2-star2-level-14) | [Level 15](#star2-star2-level-15) | [Level 16](#star2-star2-level-16) | [Level 17](#star2-star2-level-17) | [Level 18](#star2-star2-level-18) | [Level 19](#star2-star2-level-19) | [Level 20](#star2-star2-level-20)
  
<br>
  
- Level 21-30 : [Level 21](#star2-star2-star2-level-21) | [Level 22](#star2-star2-star2-level-22) | [Level 23](#star2-star2-star2-level-23) | [Level 24](#star2-star2-star2-level-24) | [Level 25](#star2-star2-star2-level-25) | [Level 26](#star2-star2-star2-level-26) | [Level 27](#star2-star2-star2-level-27) | [Level 28](#star2-star2-star2-level-28) | [Level 29](#star2-star2-star2-level-29) | [Level 30](#star2-star2-star2-level-30)
  
<br>
  
- Level 31-34 : [Level 31](#star2-star2-star2-level-31) | [Level 32](#star2-star2-star2-level-32) | [Level 33](#star2-star2-star2-level-33)


<br>
  


## :star2: Level 0


>The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**, on port 2220. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](https://overthewire.org/wargames/bandit/bandit1.html) page to find out how to beat Level 1.

<br>

:closed_lock_with_key: Connect to **bandit.labs.overthewire.org** on port 2220 with *ssh* : 
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit0``

Password : ``bandit0``

<br>

## :star2: Level 1

>The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

<br>

Use **cat** to show the content of **readme** file : 
```bash
bandit0@bandit:~$ cat readme 
NH2SXQ------------MM9H66vVXjL
bandit0@bandit:~$
```
<br>

:closed_lock_with_key: Connect with `bandit1` user and password found.

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit1``

Password  : ``NH2SXQw--------HMM9H66vVXjL``

<br>

## :star2: Level 2

>The password for the next level is stored in a file called **-** located in the home directory

<br>

We can't use ``cat -`` because it is not working. We can try another way like :
```bash
bandit1@bandit:~$ cat ./-
rRGizSaX---------TcYZWU6lgzi
bandit1@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit2`` user and password found.

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit2``

Password  : ``rRGizSa--------XTcYZWU6lgzi``

<br>

## :star2: Level 3

>The password for the next level is stored in a file called **spaces in this filename** located in the home directory

<br>

We can use two ways to read the content : 
- Use quotes : ``'filename with spaces'``
- Escape with ``\`` : ``filename\ with\ spaces\``


Try it : 
```bash
bandit2@bandit:~$ cat 'spaces in this filename' 
aBZ0W5Em--------auFJ2lAiG
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
aBZ0W5Em--------Owd8bauFJ2lAiG
bandit2@bandit:~$
```

:bulb: *Use TAB touch when you are using ssh !*

<br>

:closed_lock_with_key: Connect with ``bandit3`` user and password found.

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit3``

Password  : ``aBZ0W5E--------d8bauFJ2lAiG``

<br>

## :star2: Level 4

> The password for the next level is stored in a hidden file in the **inhere** directory.

<br>

The **ls** command will help us. Add ``-a`` switch to print hidden dir(s)/file(s) : 
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct  5  2023 .
drwxr-xr-x 3 root    root    4096 Oct  5  2023 ..
-rw-r----- 1 bandit4 bandit3   33 Oct  5  2023 .hidden
bandit3@bandit:~/inhere$ cat .hidden 
2EW7BBsr6a--------67dm8EgX26xNe
bandit3@bandit:~/inhere$
```

<br>

:closed_lock_with_key: Connect with ``bandit4`` user and password found.

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit4``

Password  : ``2EW7BBsr--------7dm8EgX26xNe``

<br>

## :star2: Level 5

> The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

<br>

There are 10 files and only one is human-readable. Use **file** to know more about type of each file : 
```bash
bandit4@bandit:~/inhere$ file -- *
-file00: data
-file01: data
-file02: data
-file03: data
-file04: data
-file05: data
-file06: data
-file07: ASCII text
-file08: data
-file09: data
```

As you can see, ``-file07`` is the only **ASCII text**. 
Now, use **cat** to show its content :
```bash
bandit4@bandit:~/inhere$ cat ./-file07 
lrIWWI6b--------OIYfr6eEeqR
bandit4@bandit:~/inhere$
```

<br>

:closed_lock_with_key: Connect with ``bandit5`` user and password found.

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit5``

Password  : ``lrIWWI6b--------qUdOIYfr6eEeqR``

<br>

## :star2: Level 6

> The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:
>	- human-readable
>	- 1033 bytes in size
>	- not executable

<br>

There are a lot of files and directories so we won't enumerate manually. With **find**,
we can search file with differents parameters as size, time, ...


Here, we know the file's size : 1033 bytes.
Use the following syntax : ``find . -size 1033c 2>/dev/null``
- ``.`` : Because I was in **inhere** directory
- ``-size 1033c`` : ``c`` is for bytes.
- ``2>/dev/null`` : Don't print errors

```bash
bandit5@bandit:~/inhere$ find . -size 1033c 2>/dev/null
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmL--------pGSfjYKqJU
```

<br>

:closed_lock_with_key: Connect with ``bandit6`` user and password found.

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit6``

Password  : ``P4L4v--------Vl7jG1ApGSfjYKqJU``

<br>

## :star2: Level 7

> The password for the next level is stored **somewhere on the server** and has all of the following properties:
>	- owned by user bandit7
>	- owned by group bandit6
>	- 33 bytes in size

<br>

Like the previous level, we will use **find** with the following syntax : 
``find / -size 33c -group bandit6 -user bandit7 2>/dev/null``
- ``-group`` : group own
- ``-user `` : user own


Execute the command : 
```bash
bandit6@bandit:~$ find / -size 33c -group bandit6 -user bandit7 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2X--------N4vzqu4v99S
bandit6@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit7`` user and password found.

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit7``

Password  : ``z7WtoNQU2Xf--------rN4vzqu4v99S``

<br>

## :star2: Level 8

> The password for the next level is stored in the file **data.txt** next to the word **millionth**

<br>

The file **data.txt** is big. We need to use **grep** to filter some text : 
```bash
bandit7@bandit:~$ wc -l data.txt 
98567 data.txt
bandit7@bandit:~$ cat data.txt | grep millionth
millionth	TESKZC0XvT--------wm25STk5iWrBvP
bandit7@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit8`` user and password found.

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit8``

Password  : ``TESKZC0XvTe--------STk5iWrBvP``

<br>

## :star2: Level 9

> The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

<br>

There are a lot of lines. We need to use **sort** and **uniq**. First, we will sort the file and use **uniq** to print the only one line of text : 
```bash
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYi--------OGSlNInNE00t
bandit8@bandit:~$
```
- ``-u`` : Only output lines that are unique in the input.

<br>

:closed_lock_with_key: Connect with ``bandit9`` user and password found.

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit9``

Password  : ``EN632PlfY--------XOGSlNInNE00t``

<br>

## :star2: Level 10

>The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

<br>

Combine **grep** and **strings** to find the password : 
```bash
bandit9@bandit:~$ strings data.txt | grep =
=2""L(
x]T========== theG)"
========== passwordk^
Y=xW
t%=q
========== is
4=}D3
{1\=
FC&=z
=Y!m
	$/2`)=Y
4_Q=\
MO=(
?=|J
WX=DA
{TbJ;=l
[=lI
========== G7w8LIi6--------LgrywtEUlyyp6s
>8=6
=r=_
=uea
zl=4	
bandit9@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit10`` user and password found.

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit10``

Password  : ``G7w8LIi6J--------ywtEUlyyp6s``

<br>

## :star2: :star2: Level 11

> The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

<br>

To read the password, we will decode it like this  : 
```bash
bandit10@bandit:~$ cat data.txt 
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ echo VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg== | base64 -d
The password is 6zPeziLd--------6nVCKzphlXHBM
bandit10@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit11`` user and password found.

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit11``

Password  : ``6zPeziLdR2R--------VCKzphlXHBM``

<br>

## :star2: :star2: Level 12

> The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

<br>

The description help us to know which encryption is used. Here, this is **rot13**.
```bash
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$
```

Go on [CyberChef](https://gchq.github.io/CyberChef/) and decrypt the strings.
The result will be : 
```
The password is JVNBBFSmZw--------8chDz5yVRv
```

<br>

:closed_lock_with_key: Connect with ``bandit12`` user and password found.

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit12``

Password  : ``JVNBBFSmZw--------W8chDz5yVRv``

<br>

## :star2: :star2: Level 13

> The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

<br>

When we try to read the **data.txt** file, we see a HexDump file. With **xxd**, we can convert this file to its previous format : 
```bash
bandit12@bandit:/tmp/testdir$ xxd -r data.txt > data.bin
bandit12@bandit:/tmp/testdir$ file data.bin 
data.bin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
```


Now, we have a **gzip** file. Extract the archive with : ``gzip -d $filename`` : 
```bash
bandit12@bandit:/tmp/testdir$ mv data.bin data.gz
bandit12@bandit:/tmp/testdir$ file data.gz
data.gz: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/testdir$ gzip -d data.gz 
bandit12@bandit:/tmp/testdir$ ls
data  data.txt
bandit12@bandit:/tmp/testdir$
```
*When you are using **gzip**, the extension need to be ``.gz`` !*


Again, we have another archive file. It is a **bzip2** file : 
```bash
bandit12@bandit:/tmp/testdir$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/testdir$ mv data data.bz2
bandit12@bandit:/tmp/testdir$ bzip2 -d data.bz2 
bandit12@bandit:/tmp/testdir$ ls
data  data.txt
bandit12@bandit:/tmp/testdir$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
```


Continue until we have a text file :
```bash
bandit12@bandit:/tmp/testdir$ mv data data.gz
bandit12@bandit:/tmp/testdir$ gzip -d data.gz 
bandit12@bandit:/tmp/testdir$ ls
data  data.txt
bandit12@bandit:/tmp/testdir$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/testdir$ mv data data.tar
bandit12@bandit:/tmp/testdir$ tar -xvf data.tar 
data5.bin
bandit12@bandit:/tmp/testdir$ ls
data5.bin  data.tar  data.txt
bandit12@bandit:/tmp/testdir$
bandit12@bandit:/tmp/testdir$ file data5.bin 
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/testdir$ mv data5.bin data5.tar
bandit12@bandit:/tmp/testdir$ tar -xvf data5.tar 
data6.bin
bandit12@bandit:/tmp/testdir$ ls
data5.tar  data6.bin  data.tar  data.txt
bandit12@bandit:/tmp/testdir$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/testdir$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/testdir$ bzip2 -d data6.bz2 
bandit12@bandit:/tmp/testdir$ ls
data5.tar  data6  data.tar  data.txt
bandit12@bandit:/tmp/testdir$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/testdir$
bandit12@bandit:/tmp/testdir$ tar -xvf data6
data8.bin
bandit12@bandit:/tmp/testdir$ ls
data5.tar  data6  data8.bin  data.tar  data.txt
bandit12@bandit:/tmp/testdir$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/testdir$ gzip -d data8.bin
gzip: data8.bin: unknown suffix -- ignored
bandit12@bandit:/tmp/testdir$ mv data8.bin data8.gz
bandit12@bandit:/tmp/testdir$ gzip -d data8.gz 
bandit12@bandit:/tmp/testdir$ ls
data5.tar  data6  data8  data.tar  data.txt
bandit12@bandit:/tmp/testdir$ file data8 
data8: ASCII text
bandit12@bandit:/tmp/testdir$ cat data8
The password is wbWdlB--------PhauuOo6pwRmrDw
bandit12@bandit:/tmp/testdir$
```

We have the password ! 

<br>

:closed_lock_with_key: Connect with ``bandit13`` user and password found.

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit13``

Password  : ``wbWdlB--------aPhauuOo6pwRmrDw``

<br>

## :star2: :star2: Level 14

>The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on.

<br>

On the current directory, there is a ssh private key : 
```bash
bandit13@bandit:~$ cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
----------------------REDACTED----------------------------------
```


Copy/paste the content in a new file. Change permissions to 600 with ``chmod 600 file_rsa``, and connect with **ssh** : 
``ssh -i bandit14_rsa bandit14@bandit.labs.overthewire.org -p 2220``

<br>

:closed_lock_with_key: Connect with ``bandit14`` user and ssh key found.

```bash
ssh -i bandit14_rsa bandit14@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit14``

SSH key : ``bandit14_rsa``

<br>

## :star2: :star2: Level 15

> The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

<br>

To connect on port 30000 on localhost, we will use **netcat** : 
```bash
bandit14@bandit:~$ nc localhost 30000
dd
Wrong! Please enter the correct current password
```
We need the current password. Remember that it was in ``/etc/bandit_pass/bandit14`` *(previous level description)*.
So read the content with **cat** : 
```bash
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC--------OiF0ENq
bandit14@bandit:~$
```


Now, return on port 30000 and submit the current password : 
```bash
bandit14@bandit:~$ nc localhost 30000
fGrHPx40--------WFTOiF0ENq
Correct!
jN2kgmIXJ--------4Zcka6tnt

^C
bandit14@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit15`` user and password found.

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit15``

Password  : ``jN2kgmIXJ--------n4Zcka6tnt``

<br>

## :star2: :star2: Level 16

> The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.
>**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

<br>

We need to use **SSL** encryption. We will use **openssl** command with the following syntax to connect on port 30001 : 
```bash
openssl s_client -connect localhost:30001
```

Wait for ``read R BLOCK`` message and submit current password : 
```bash
read R BLOCK
jN2kgmIXJ-----------tn4Zcka6tnt
Correct!
JQttfApK-----------GR50qclOAil1

closed
bandit15@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit16`` user and password found.

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit16``

Password  : ``JQttfApK4---------SXGR50qclOAil1``

<br>

## :star2: :star2: Level 17

>The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

<br>

We will use **nmap** to discover open ports : 
```bash
bandit16@bandit:~$ nmap localhost -p31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2024-04-09 18:28 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.09 seconds
```

There are 5 open ports. We can use **openssl** on each port to see if we will have the password : ``openssl s_client -connect localhost:$PORT``

- 31046 :x:
- 31518 :x:
- 31691 :x:
- 31790 :white_check_mark:

```bash
---
read R BLOCK
JQttfApK---------0qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0---------------------------------------------X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit17`` user and ssh key found.

```bash
ssh -i bandit17_rsa bandit17@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit17``

SSH key : ``bandit17_rsa``

<br>

## :star2: :star2: Level 18

> There are 2 files in the home directory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**
> 
> **NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

<br>

Here, the **diff** tool will be useful. It compares two files line per line.
Use the following syntax : ``diff file1 file2``

```bash
bandit17@bandit:~$ diff passwords.new passwords.old 
42c42
< hga5tuuCL---------iMN8ssu9LFrdg
---
> p6ggwdNHncn---------KtKVq185ZU7AW
bandit17@bandit:~$ grep 'hga5tuuCL---------giMN8ssu9LFrdg' passwords.new 
hga5tuu---------nagiMN8ssu9LFrdg
bandit17@bandit:~$
```

Use **grep** to check if the password is in ``passwords.new``.

<br>

:closed_lock_with_key: Connect with ``bandit18`` user and password found.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit18``

Password  : ``hga5tuuCL---------MN8ssu9LFrdg``

<br>

## :star2: :star2: Level 19

> The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

<br>

If you try to connect with **ssh**, you will be logout instantly.

Thanks to **ssh** service, we can execute directly a command. Here, we know that there is a ``readme`` file in home directory. So, we could : 
``ssh bandit18@bandit.labs.overthewire.org -p 2220 'cat readme'``

And the output is :
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 'cat readme'
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
awhqfNnA---------F95h7HoMTrC
```

<br>

:closed_lock_with_key: Connect with ``bandit19`` user and password found.

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit19``

Password  : ``awhqfNnAb---------F95h7HoMTrC``

<br>

## :star2: :star2: Level 20

> To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

<br>

There is a setuid file which is interesting.
Execute the file to see what is happening : 
```bash
bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$
```

It seems that we can execute command. Because it is a setuid file, the command will be executed as ``bandit20``. So, we can pop a shell : 
```bash
bandit19@bandit:~$ ./bandit20-do bash -p
bash-5.1$ id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bash-5.1$
```

:warning: *Don't forget to use ``-p`` for privileged mode !*

Now, go on ``/etc/bandit_pass`` directory and get the password : 
```bash
bash-5.1$ cd /etc/bandit_pass
bash-5.1$ ls
bandit0   bandit13  bandit18  bandit22	bandit27  bandit31  bandit6
bandit1   bandit14  bandit19  bandit23	bandit28  bandit32  bandit7
bandit10  bandit15  bandit2   bandit24	bandit29  bandit33  bandit8
bandit11  bandit16  bandit20  bandit25	bandit3   bandit4   bandit9
bandit12  bandit17  bandit21  bandit26	bandit30  bandit5
bash-5.1$ cat bandit20 
VxCazJaVy---------U0mJTCM8rR95XT
bash-5.1$
```

<br>

:closed_lock_with_key: Connect with ``bandit20`` user and password found.

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit20``

Password  : ``VxCazJa---------BU0mJTCM8rR95XT``

<br>

## :star2: :star2: :star2: Level 21

> There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
> 
> **NOTE:** Try connecting to your own network daemon to see if it works as you think

<br>

First, we need to setup a listener with **netcat** on the port of your choice :
``nc -lp 1234`` 

*(⚠️ On victim's machine !)* 


Then, connect to port 1234 with the setuid file : 
```bash
./suconnect 1234
```

Now, send the current password of ``bandit20`` on the **netcat** listener :
```bash
bandit20@bandit:~$ nc -lp 1234
VxCazJaVyk---------U0mJTCM8rR95XT
NvEJF7oVjk---------EFOllh9V1IBcq
```

The new password appears ! 
Return on setuid file to confirm : 
```bash
bandit20@bandit:~$ ./suconnect 1234
Read: VxCazJaVyk---------0mJTCM8rR95XT
Password matches, sending next password
bandit20@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit21`` user and password found.

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit21``

Password  : ``NvEJF7oVjk---------KEFOllh9V1IBcq``

<br>

## :star2: :star2: :star2: Level 22

> A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

<br>

Go in ``/etc/cron.d`` directory. There is a ``cronjob_bandit22`` file : 
```bash
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$
```

We can see that ``bandit22`` execute a specific command : ``/usr/bin/cronjob_bandit22.sh &> /dev/null``

Read the **.sh** file with ``cat`` : 
```bash
bandit21@bandit:~$ ls -la /usr/bin/cronjob_bandit22.sh
-rwxr-x--- 1 bandit22 bandit21 130 Oct  5  2023 /usr/bin/cronjob_bandit22.sh
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$
```

The output of the ``/etc/bandit_pass/bandit22`` goes in  ``/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv``. 

Maybe, we could read ``/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`` : 
```bash
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdT---------mGlwngMfj4EZff
bandit21@bandit:~$
```

Yes we can ! 

<br>

:closed_lock_with_key: Connect with ``bandit22`` user and password found.

```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit22``

Password  : ``WdDozAdTM2---------lwngMfj4EZff``

<br>

## :star2: :star2: :star2: Level 23

> A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
>
> **NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

<br>

Like the previous level, there is a cron job. 
```bash
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ ls -la /usr/bin/cronjob_bandit23.sh
-rwxr-x--- 1 bandit23 bandit22 211 Oct  5  2023 /usr/bin/cronjob_bandit23.sh
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:/etc/cron.d$
```

Here, we need to understand the script. If we know the ``$mytarget`` variable, we could be able to read ``/tmp/$mytarget``.

The following line is interesting : ``mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)``

It is a simple command and ``$myname`` is the current username.
So, try to execute the same command with ``bandit23`` instead of ``$mytaget`` :
```bash
bandit22@bandit:/etc/cron.d$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
```
This MD5 hash will be the file in ``/tmp``.

Read the content with : 
```bash
bandit22@bandit:/etc/cron.d$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA67---------Quhoz8SyR2G
bandit22@bandit:/etc/cron.d$
```

<br>

:closed_lock_with_key: Connect with ``bandit23`` user and password found.

```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit23``

Password  : ``QYw0Y2aiA6---------uTQuhoz8SyR2G``

<br>

## :star2: :star2: :star2: Level 24

> A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
> 
>**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level !
>
>**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around …

<br>

Like the previous level, there is a cron job.
The script executed : 
```bash
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(l)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```

It seems that it execute and delete scripts in ``/var/spool/bandit24/foo/`` directory.
Check if we can write in this folder : 
```bash
bandit23@bandit:/var/spool/bandit24/foo$ ls -l /var/spool/bandit24/
total 248
drwxrwx-wx 20 root bandit24 249856 Apr  9 21:32 foo
bandit23@bandit:/var/spool/bandit24/foo$ 
```

Yes ! We could create a shell script.

There are many ways to exploit this. I will use this one : 
- Copy ``/etc/bandit_pass/bandit24`` file in ``/tmp/test1234``
- Change permissions
- Create a file to prove the exploitation

The script looks like this : 
```bash
bandit23@bandit:/tmp/test1234$ cat shell 
#!/bin/bash

cp /etc/bandit_pass/bandit24 /tmp/test1234/passwd
chmod 777 /tmp/test1234/passwd
touch /tmp/test1234/pwned.txt
bandit23@bandit:/tmp/test1234$
```

Move the script in ``/var/spool/bandit24/foo/`` and wait.
```bash
bandit23@bandit:/tmp/test1234$ ls
passwd  pwned.txt  shell
bandit23@bandit:/tmp/test1234$ cat passwd 
VAfGXJ1P---------8p759leLZ9GGar
bandit23@bandit:/tmp/test1234$
```

:warning: *Don't forget to change permissions on your ``/tmp`` folder !* 


It works ! 

<br>

:closed_lock_with_key: Connect with ``bandit24`` user and password found.

```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit24``

Password  : ``VAfGXJ1PB---------jI8p759leLZ9GGar``

<br>

## :star2: :star2: :star2: Level 25

> A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
   You do not need to create new connections each time

<br>

We can't do that manually, so we need to create a file with ``password PIN`` on each line.
I personally used python to create a script which generate 10000 PIN : 
```python
file_path = 'final2.txt'  

with open(file_path, 'w') as file:
    for pin in range(5000, 10000):
        line = 'VAfGXJ1PBS--------8p759leLZ9GGar {:04d}\n'.format(pin)
        file.write(line)

print(f"File '{file_path}' created.")
```

:warning: Execute the script two times because the program didn't respond after ~6000 try.

Use this following syntax to send each line to the program : 
```bash
bandit24@bandit:/tmp/test1234$ nc localhost 30002 < final2.txt 
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
------------------REDACTED-------------------------
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu---------h9UvD0O9hpx8d

Exiting.
bandit24@bandit:/tmp/test1234$
```

It works ! 

<br>

:closed_lock_with_key: Connect with ``bandit25`` user and password found.

```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit25``

Password  : ``p7TaowMYrmu2---------D0O9hpx8d``

<br>

## :star2: :star2: :star2: Level 26

>Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

<br>

There is a SSH key in the home directory. When we try to connect with ``bandit26``, we are logged out. 

Find the shell used by ``bandit26`` with : 
```bash
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$
```

It used ``showtext``. I don't know what it is. Check the script : 
```bash
bandit25@bandit:~$ cat /usr/bin/showtext 
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
bandit25@bandit:~$
```

It is using **more**. In interactive mode, we can pop a shell.
The file ``test.txt`` is too short so it can be print without interactive mode.
We need to resize our terminal's size to the smallest.
Then we will be able to execute commands : 
Press ``v`` touch,
``:set shell=/bin/bash`` and 
``:shell``

Now we have a bash shell !
```bash
bandit26@bandit:~$ id
uid=11026(bandit26) gid=11026(bandit26) groups=11026(bandit26)
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ cat /etc/bandit_pass/bandit26 
c7GvcKlw---------FstuAIBw1o1
bandit26@bandit:~$
```

<br>

:closed_lock_with_key: Connect with ``bandit26`` user and password found.

```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit26``

Password  : ``c7GvcKlw9---------7nwFstuAIBw1o1``

<br>

## :star2: :star2: :star2: Level 27

> Good job getting a shell! Now hurry and grab the password for bandit27!

<br>

We have the setuid binary which can execute command as ``bandit27``.
Use it to spawn a shell and get the password for ``bandit27`` :
```bash
bandit26@bandit:~$ ./bandit27-do bash -p
bash-5.1$ 
bash-5.1$ id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bash-5.1$ cd /etc/bandit_pass/
bash-5.1$ cat bandit27 
YnQpB---------k70ZmqkhUU2EuaS
bash-5.1$
```

<br>

:closed_lock_with_key: Connect with ``bandit27`` user and password found.

```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit27``

Password  : ``YnQp---------UFk70ZmqkhUU2EuaS``

<br>

## :star2: :star2: :star2: Level 28

> There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.
> Clone the repository and find the password for the next level.

<br>

To clone the repository, we will use **git** with the following syntax :
```bash
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
```

Clone it in a ``/tmp`` folder. Explore and read the ``README`` file : 
```bash
bandit27@bandit:/tmp/test1234/repo$ ls -la
total 16
drwxrwxr-x 3 bandit27 bandit27 4096 Apr 11 11:10 .
drwxrwxr-x 3 bandit27 bandit27 4096 Apr 11 11:10 ..
drwxrwxr-x 8 bandit27 bandit27 4096 Apr 11 11:10 .git
-rw-rw-r-- 1 bandit27 bandit27   68 Apr 11 11:10 README
bandit27@bandit:/tmp/test1234/repo$ cat README 
The password to the next level is: AVanL1---------uw35rjaOM19nR
bandit27@bandit:/tmp/test1234/repo$
```

<br>

:closed_lock_with_key: Connect with ``bandit28`` user and password found.

```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit28``

Password  : ``AVanL161y9rs---------5rjaOM19nR``

<br>

## :star2: :star2: :star2: Level 29

> There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.
> Clone the repository and find the password for the next level.

<br>

Like the previous level, clone the repository.
```bash
git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
```

There is a ``README`` file. Try to read it : 
```bash
bandit28@bandit:/tmp/test123/repo$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/test123/repo$
```

It seems that the password field was changed. Thanks to commits, we can see the previous version(s) of the ``README`` file with ``git show`` : 
```bash
bandit28@bandit:/tmp/test123/repo$ git show
commit 14f754b3ba6531a2b89df6ccae6446e8969a41f3 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:41 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: tQKvmcw---------SI3ShmsrQZK8S
+- password: xxxxxxxxxx
```

And there is the password !

<br>

:closed_lock_with_key: Connect with ``bandit29`` user and password found.

```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit29``

Password  : ``tQKvmcwNYcF---------ShmsrQZK8S``

<br>

## :star2: :star2: :star2: Level 30

> There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.
> Clone the repository and find the password for the next level.

<br>

Like the previous level, clone the repository.
```bash
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
```

Here, ``git show``won't be useful.
Enumerate the ``.git`` folder and look at ``packed-refs`` file : 
```bash
bandit29@bandit:/tmp/testdir123/repo/.git$ cat packed-refs 
# pack-refs with: peeled fully-peeled sorted 
1d160de5f8f647f00634bbf3d49b9244275217b6 refs/remotes/origin/dev
4364630b3b27c92aff7b36de7bb6ed2d30b60f88 refs/remotes/origin/master
07b750deb96fe4c903a3f93e41518adb3866f336 refs/remotes/origin/sploits-dev
```

There are other commits. Use ``git show 'COMMIT-ID'``: 
```bash
bandit29@bandit:/tmp/testdir123/repo/.git$ git show '1d160de5f8f647f00634bbf3d49b9244275217b6'
commit 1d160de5f8f647f00634bbf3d49b9244275217b6 (origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Oct 5 06:19:43 2023 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials
 
 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3H---------Pzc2L6y9EOnS
 
bandit29@bandit:/tmp/testdir123/repo/.git$
```

A password was added ! 

<br>

:closed_lock_with_key: Connect with ``bandit30`` user and password found.

```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit30``

Password  : ``xbhV3HpN---------2L6y9EOnS``

<br>

## :star2: :star2: :star2: Level 31

> There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.
> Clone the repository and find the password for the next level.

<br>

Like the previous level, clone the repository.
```bash
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
```

This level is similar to the previous. Read the ``packed-refs`` file and show the ``secret`` commit : 
```bash
bandit30@bandit:/tmp/testdir1234/repo/.git$ cat packed-refs 
# pack-refs with: peeled fully-peeled sorted 
d39631d73f786269b895ae9a7b14760cbf40a99f refs/remotes/origin/master
831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret
bandit30@bandit:/tmp/testdir1234/repo/.git$ git show '831aac2e2341f009e40e46392a4f5dd318483019'
OoffzGDl---------z1D41JW1Mhmt
bandit30@bandit:/tmp/testdir1234/repo/.git$
```

<br>

:closed_lock_with_key: Connect with ``bandit31`` user and password found.

```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit31``

Password  : ``OoffzGDl---------z1D41JW1Mhmt``

<br>

## :star2: :star2: :star2: Level 32

> There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.
> Clone the repository and find the password for the next level.

<br>

Clone the repository and read the ``README`` file : 
```bash
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```

It seems that we need to push a file ``key.txt`` to the repository.

This is the steps to follow : 

1. ``touch key.txt`` : Create the new file
2. ``echo 'May I come in?' > key.txt`` : Add text
3. ``git add key.txt`` : Add file
4. ``git status`` : Check
5. ``git commit -m 'I'm uploading file !'`` : Add a message
6. ``git push origin master`` : Save and send

Once you submit the password, you will have this message with the next password :

```bash
bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 316 bytes | 316.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y5---------TVL5dW8y 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/testtest/repo$
```

<br>

:closed_lock_with_key: Connect with ``bandit32`` user and password found.

```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```

Username : ``bandit32``

Password  : ``rmCBvG56------------dO7ATVL5dW8y``

<br>

## :star2: :star2: :star2: Level 33

*Coming soon !*


<br> 

<br> 

# Conclusion 

Bandit was the first lab of the platform. The next will be [Natas](https://overthewire.org/wargames/natas).

Thanks for reading ! 
