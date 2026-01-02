# BANDIT LEVELS 6-10:

## Bandit level 6-7:

-> **Level goal**: The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7,
owned by group bandit6,
33 bytes in size

-> **Commands used**: 

```ssh bandit6@bandit.labs.overthewire.org -p 2220```

```bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c```

find: ‘/proc/tty/driver’: Permission denied

find: ‘/var/lib/polkit-1’: Permission denied

find: ‘/var/lib/chrony’: Permission denied

find: ‘/var/lib/udisks2’: Permission denied

find: ‘/var/lib/snapd/cookie’: Permission denied

find: ‘/var/lib/snapd/void’: Permission denied

find: ‘/var/lib/private’: Permission denied

find: ‘/var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied

/var/lib/dpkg/info/bandit7.password

```bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password```

morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj   (password)

```bandit6@bandit:~$ exit```

logout

Connection to bandit.labs.overthewire.org closed.

```$ ssh bandit7@bandit.labs.overthewire.org -p 2220```

--> logging in into this server using the given password. 

## Bandit level 7-8:

-> **Level goal**: The password for the next level is stored in the file data.txt next to the word millionth.

-> **Commands used**: 

```bandit7@bandit:~$ ls```

data.txt

```bandit7@bandit:~$ cat data.txt```

--> strings of files, characters came and we had to sort them out to find the password.

```bandit7@bandit:~$ strings data.txt | grep "millionth"```

millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

```bandit7@bandit:~$ exit```

logout

```ssh bandit8@bandit.labs.overthewire.org -p 2220```

--> logging in into the server using the password.

## Bandit level 8-9:

-> **Level goal**: The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

-> **Commands used**: 

```bandit8@bandit:~$ ls```

data.txt

```bandit8@bandit:~$ cat data.txt```

eEAA4ytk957MspwYKLeOgooPzJKOg8jY

VVamYLR8vQaPhZV8sFPh7NVrqt3cwx5E

q9C0UQZ52GznEieTtXOgPrVvIvB60jxL

1kopVbuefPoyJ5GDXH0q46SXQVQQZmge   (many other countless character strings got printed and we needed to sort them)

```bandit8@bandit:~$ sort data.txt | uniq -c```

     10 1kopVbuefPoyJ5GDXH0q46SXQVQQZmge
     
     10 1PIVQI2GADz12PtZBMarRD3DpMfDoxbG
     
     10 1S7LmjYT5AlAvRmzK8ksutVRWlMel92r
     
     10 2EFKJco5KZnbkQLj0oen5cVgbwzNioDr
     
     10 2rTFFlUJ4KkcEGhrsi6o5QsgofP8yTyr
     
     10 3XiARLa3d6LTJ5PYT5JCfN60VDx6FLVH
     
      1 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM  (the password we need)

```bandit8@bandit:~$ exit```

logout

```ssh bandit9@bandit.labs.overthewire.org -p 2220```

--> logging in into this server with the password.

## Bandit level 9-10:

-> **Level goal**: The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

-> **Commands used**: 

```bandit9@bandit:~$ ls -alps```

total 40

 4 drwxr-xr-x   2 root     root     4096 Oct 14 09:25 ./
 
 4 drwxr-xr-x 150 root     root     4096 Oct 14 09:29 ../
 
 4 -rw-r--r--   1 root     root      220 Mar 31  2024 .bash_logout
 
 4 -rw-r--r--   1 root     root     3851 Oct 14 09:19 .bashrc
 
20 -rw-r-----   1 bandit10 bandit9 19382 Oct 14 09:25 data.txt

 4 -rw-r--r--   1 root     root      807 Mar 31  2024 .profile
 
```bandit9@bandit:~$ strings data.txt | grep "="```

FB`=


c\5D=

========== the

?/=l

=Uc1

=vG*2P

========== password

k=ezG

E========== is

=%r_

.?=Dm

O&A=n

5========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey (password)

=*^Y

=L3jT

q<=,

'QHE=

+=NBf

```bandit9@bandit:~$ exit```

logout

```ssh bandit10@bandit.labs.overthewire.org -p 2220```

--> logging in into the server using the password that we retrieved. 

## Bandit levels 10-11:

-> **Level goal**: The password for the next level is stored in the file data.txt, which contains base64 encoded data.

-> **Commands used**: 

```bandit10@bandit:~$ ls```

data.txt

```bandit10@bandit:~$ cat data.txt```

VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==  (this is base64 encoded format and we needed to decode it to get the actual password.)

```bandit10@bandit:~$ man base64```

```bandit10@bandit:~$ base64 -d data.txt```

The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

```bandit10@bandit:~$ exit```

logout

```ssh bandit11@bandit.labs.overthewire.org -p 2220```

--> logging in into this server using the password. 

## --> *Completed levels 6-10*
