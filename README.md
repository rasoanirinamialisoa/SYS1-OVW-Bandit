# SYS1
Solutions jeux Bandits - OverTheWire
## _BANDIT_
# Niveau 0
ssh bandit8@bandit.labs.overthewire.org -p 2220
# Niveau 0 → Niveau 1
- bandit0@bandit:~$ cat ~/readme
mot de passe : 
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
- bandit0@bandit:~$ exit

# Niveau 1 → Niveau  2
- bandit1@bandit:~$ ls
- '-'
- bandit1@bandit:~$ cat ./-
mot de passe : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

# Niveau 2 → Niveau  3
- bandit2@bandit:~$ ls
- spaces in this filename
- bandit2@bandit:~$ cat 'spaces in this filename'
- mot de passe : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

# Niveau 3→ Niveau  4
- bandit3@bandit:~$ ls
- inhere
- bandit3@bandit:~$ cd inhere/
- bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
- bandit3@bandit:~/inhere$ cat .hidden
mot de passe : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

# Niveau 4 → Niveau 5
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ file inhere/*
> inhere/-file00: data
> inhere/-file01: data
> inhere/-file02: data
inhere/-file03: data
inhere/-file04: data
inhere/-file05: data
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
inhere/-file09: Non-ISO extended-ASCII text, with no line terminators

- bandit4@bandit:~$ cat inhere/-file07
- lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

# Niveau 5 → Niveau  6
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
> maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
> maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
> maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
> maybehere03  maybehere07  maybehere11  maybehere15  maybehere19

bandit5@bandit:~/inhere$ find -maxdepth 2 -type f -size 1033c
./maybehere07/.file2

bandit5@bandit:~/inhere$ cat ./maybehere07/file2
cat: ./maybehere07/file2: No such file or directory
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

# Niveau 6 → Niveau  7
- bandit6@bandit:~$  pwd
- '/home/bandit6'
- bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
- /var/lib/dpkg/info/bandit7.password
- bandit6@bandit:~$ /var/lib/dpkg/info/bandit7.password
- bash: /var/lib/dpkg/info/bandit7.password: Permission denied
- bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
- z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

# Niveau 7 → Niveau 8
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ nano data.txt
^W
millionth
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

# Niveau 8 → Niveau 9
- bandit8@bandit:~$ sort data.txt | uniq -u
- EN632PlfYiZbn3PhVK3XOGSlNInNE00t

# Niveau 9 → Niveau 10
- bandit9@bandit:~$ strings data.txt
- ========== 
- G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

# Niveau 10 → Niveau 11
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

# Niveau 11 → Niveau  12
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ echo | cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

# Niveau 12 → Niveau 13
bandit12@bandit:mkdir /tmp/gxuvimr$
bandit12@bandit:cd /tmp/gxuvimr$
bandit12@bandit:/tmp/gxuvimr$ xxd -r data.txt > data
__
bandit12@bandit:/tmp/gxuvimr$ ls
data  data.txt

bandit12@bandit:/tmp/gxuvimr$ file data
data: gzip compressed data, was "data2.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/gxuvimr$ mv data data.gz
bandit12@bandit:/tmp/gxuvimr$ gzip -d data.gz

bandit12@bandit:/tmp/gxuvimr$
bandit12@bandit:/tmp/gxuvimr$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/gxuvimr$ mv data data.bz2
bandit12@bandit:/tmp/gxuvimr$ bzip2 -d data.bz2

bandit12@bandit:/tmp/gxuvimr$ file data
data: gzip compressed data, was "data4.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/gxuvimr$ mv data data.gz
bandit12@bandit:/tmp/gxuvimr$ gzip -d data.gz

bandit12@bandit:/tmp/gxuvimr$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/gxuvimr$ mv data data.tar
bandit12@bandit:/tmp/gxuvimr$ tar -xvf data.tar
data5.bin
bandit12@bandit:/tmp/gxuvimr$ ls
data5.bin  data.tar  data.txt

bandit12@bandit:/tmp/gxuvimr$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/gxuvimr$ mv data5.bin data5.tar
bandit12@bandit:/tmp/gxuvimr$ tar -xvf data5.tar
data6.bin

bandit12@bandit:/tmp/gxuvimr$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/gxuvimr$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/gxuvimr$ bzip2 -d data6.bz2

bandit12@bandit:/tmp/gxuvimr$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/gxuvimr$ mv data6 data6.tar
bandit12@bandit:/tmp/gxuvimr$ tar -xvf data6.tar
data8.bin

bandit12@bandit:/tmp/gxuvimr$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/gxuvimr$ mv data8.bin data8.gz
bandit12@bandit:/tmp/gxuvimr$ gzip -d data8.gz

bandit12@bandit:/tmp/gxuvimr$ file data8
data8: ASCII text
bandit12@bandit:/tmp/gxuvimr$ cat data8
The password is : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

# Niveau 13 → Niveau  14
bandit13@bandit:~$ ls
sshkey.private
ssh -i sshkey.private -p 2220 bandit14@localhost
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

# Niveau 14 → Niveau 15
bandit14@bandit:~$ nc localhost 30000 < /etc/bandit_pass/bandit14
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

# Niveau 15→ Niveau  16
bandit15@bandit:~$ openssl s_client -connect localhost:30001 -quiet < /etc/bandit_pass/bandit15
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=May  5 11:21:25 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=May  5 11:21:25 2023 GMT
verify return:1
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

# Niveau 16 → Niveau  17
bandit16@bandit:~$ nmap -sV -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-05-06 19:52 UTC
Stats: 0:01:07 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 80.00% done; ETC: 19:54 (0:00:17 remaining)

Nmap scan report for localhost (127.0.0.1)
Host is up (0.00012s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE     VERSION
> 31046/tcp open  echo
> 31518/tcp open  ssl/echo
> 31691/tcp open  echo
> 31790/tcp open  ssl/unknown
> 31960/tcp open  echo
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 98.11 seconds

bandit16@bandit:~$ openssl s_client -connect localhost:31790 -quiet < /etc/bandit_pass/bandit16
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=May  5 11:21:24 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=May  5 11:21:24 2023 GMT
verify return:1
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
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
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

bandit16@bandit:~$ PRIVATE_KEY=$(mktemp)
bandit16@bandit:~$ openssl s_client \
  -connect localhost:31790 \
  -quiet < /etc/bandit_pass/bandit16 > $PRIVATE_KEY
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=May  5 11:21:24 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=May  5 11:21:24 2023 GMT
verify return:1
bandit16@bandit:~$ ssh -i $PRIVATE_KEY -p 2220 bandit17@localhost
bandit17@bandit:~$


# Niveau 17 → Niveau  18
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< glZreTEH1V3cGKL6g4conYqZqaEj0mte
Good password : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

# Niveau 18 → Niveau  19
Byebye !
Connection to bandit.labs.overthewire.org closed.
ssh -p 2220 bandit18@bandit.labs.overthewire.org cat readme
bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

# Niveau 19 → Niveau  20
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ id
uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

# Niveau 20 → Niveau  21

PC1
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ man nc
bandit20@bandit:~$ man nc
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ ./suconnect 9999
Read: 46bCDdFhklNnrStUuvZz
ERROR: This doesn't match the current password!
bandit20@bandit:~$ ./suconnect 8080
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
bandit20@bandit:~$

PC2

bandit20@bandit:~$ nc -lvp 9999
Listening on 0.0.0.0 9999
Connection received on localhost 36056
46bCDdFhklNnrStUuvZz
FAIL!
bandit20@bandit:~$ nc -lvp 8000
nc: Address already in use
bandit20@bandit:~$ nc -lvp 8080
Listening on 0.0.0.0 8080
Connection received on localhost 37696
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
good password : NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

# Niveau 21 → Niveau  22
bandit21@bandit:~$ ls -l /etc/cron.d
total 36
-rw-r--r-- 1 root root  62 Apr 23 18:04 cronjob_bandit15_root
-rw-r--r-- 1 root root  62 Apr 23 18:04 cronjob_bandit17_root
-rw-r--r-- 1 root root 120 Apr 23 18:04 cronjob_bandit22
-rw-r--r-- 1 root root 122 Apr 23 18:04 cronjob_bandit23
-rw-r--r-- 1 root root 120 Apr 23 18:04 cronjob_bandit24
-rw-r--r-- 1 root root  62 Apr 23 18:04 cronjob_bandit25_root
-rw-r--r-- 1 root root 201 Jan  8  2022 e2scrub_all
-rwx------ 1 root root  52 Apr 23 18:05 otw-tmp-dir
-rw-r--r-- 1 root root 396 Feb  2  2021 sysstat
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
 bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

# Niveau 22 → Niveau  23

bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo I am user bandit23 | md5sum
8ca319486bfbbc3663ea0fbe81326349  -
8ca319486bfbbc3663ea0fbe81326349  -
8ca319486bfbbc3663ea0fbe81326349: command not found
bandit22@bandit:~$ echo I am user bandit23 | md5sum
8ca319486bfbbc3663ea0fbe81326349
8ca319486bfbbc3663ea0fbe81326349  -
8ca319486bfbbc3663ea0fbe81326349: command not found
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
- QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

# Niveau 23 → Niveau  24


# Niveau 24 → Niveau  25
# Niveau 25 → Niveau  26
# Niveau 26 → Niveau  27
# Niveau 27 → Niveau  28
# Niveau 28 → Niveau  29
# Niveau 29 → Niveau  30
# Niveau 30 → Niveau 31
# Niveau 31 → Niveau 32
# Niveau 31 → Niveau  33
# Niveau 33 → Niveau  34
# Niveau 34 → N
