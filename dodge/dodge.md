# CTF Name: Challenge name

![date](https://img.shields.io/badge/date-05.24.1970-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![misc category](https://img.shields.io/badge/category-misc-lightgrey.svg)
![score](https://img.shields.io/badge/score-25-blue.svg)
![solves](https://img.shields.io/badge/solves-59-brightgreen.svg)

## Description
I catched your cat. Can you dodge it?  
ssh ctf@61.28.237.24 -p30400 password: hcmus-ctf

## Author
pakkunandy

## Attached files
None

## Summary
use echo $(<flag.txt)

## Flag
```
HCMUS-CTF{You_know_some_command_line_stuff}
```

## Detailed solution
After connecting, a message was printed out:
```
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.10.12-200.fc33.x86_64 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Last login: Sun May 23 17:38:32 2021 from 10.76.0.4
```
This indicates that some packages and commands may not be on this server and therefore cannot work.  
I ran ```ls``` to see the content of the directory:
```
bin  flag.txt
```
I tried to use ```cat flag.txt```
```
-rbash: cat: command not found
```
I tried ```echo $(<flag.txt)```:
```
HCMUS-CTF{You_know_some_command_line_stuff}
```
