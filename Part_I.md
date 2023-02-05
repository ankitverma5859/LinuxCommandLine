# Part I : Learning the Shell

#### Chapter 1: What is Shell?
- The shell is a program that takes keyboard commands and passes them to the operating system to carry out. 
- Almost all Linux distributions supply a shell program from the GNU Project called **bash**. 
- The name is an acronym for **b**ourne-**a**gain **sh**ell, a reference to the fact that bash is an enhanced replacement for sh, the original Unix shell program written by Steve Bourne.
- When using a graphical user interface (GUI), we need another program called a terminal emulator to interact with the shell.

##### Shell Prompt
- Typically a shell prompt appears with ***username@machinename*** followed by the current working directory and a dollar sign($) or a hash(#) if it is superuser.
```
user@ubn-3620:~$ 
user@ubn-3620:~$ sudo -s 
root@ubn-3620:~# 
```
- Up and Down arrow can be used to move through the commands already entered. This is called command history.
- Most Linux Distributions remember 1000 commands.

##### Some more useful commands
> Date
```
root@ubn-3620:~# date
Sun Feb  5 16:25:47 IST 2023
```

> Calender
```
root@ubn-3620:~# cal
   February 2023
Su Mo Tu We Th Fr Sa
          1  2  3  4
 5  6  7  8  9 10 11
12 13 14 15 16 17 18
19 20 21 22 23 24 25
26 27 28
```

> Used Space
```
root@ubn-3620:~# df
Filesystem     1K-blocks      Used Available Use% Mounted on
udev             1937432         0   1937432   0% /dev
tmpfs             392248      2012    390236   1% /run
/dev/sda6      287254816 262778504   9811508  97% /
tmpfs            1961232        16   1961216   1% /dev/shm
tmpfs               5120         4      5116   1% /run/lock
```

> Free Space
```
root@ubn-3620:~# free
              total        used        free      shared  buff/cache   available
Mem:        3922464      772944     1130292      238516     2019228     2633224
Swap:       7812092      478976     7333116
```

#### Chapter 2: Navigation

> Print Current Working Directory
```
root@ubn-3620:~# pwd
/home/user
```

> List Directory Dontents
```
root@ubn-3620:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Untitled.ipynb  Videos  anaconda3  examples.desktop  f.cpp  f.h  f.o  snap
```

> Change Directory
```
root@ubn-3620:~# cd Documents
root@ubn-3620:~/Documents#
```

> Change to Home Directory (cd )
```
root@ubn-3620:~# cd Documents/
root@ubn-3620:~/Documents# cd
root@ubn-3620:~#
```

> Change to Previous Directory (cd -)
```
root@ubn-3620:~# cd Documents/
root@ubn-3620:~/Documents# cd
root@ubn-3620:~# cd -
/home/user/Documents
root@ubn-3620:~/Documents#
```

> Change to Home Directory of a particular user
```
cd ~username
```

> Current Working Directory
```
. (dot)
```

> Current Working Directory's Parent Directory
```
.. (dot dot)
```

#### Chapter 3:

> List the contents of the Current Directory
```
root@ubn-3620:~# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Untitled.ipynb  Videos  anaconda3  examples.desktop  f.cpp  f.h  f.o  snap
```

> List the contents of a Path
```
root@ubn-3620:~# ls ~/Documents
f  mtp
```

> List the contents of multiple paths. Here, HOME and /Documents
```
root@ubn-3620:~# ls ~ ~/Documents
/home/user:
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Untitled.ipynb  Videos  anaconda3  examples.desktop  f.cpp  f.h  f.o  snap

/home/user/Documents:
f  mtp
```


> Commands are followed by one or more ***options*** that modify their ***behaviours***, and further by one or more arguments.
```
command -options arguments
```

> -- long option - short option

> Long Option
```
root@ubn-3620:~/Downloads# ls -l
total 2484376
-rw-rw-r-- 1 user user 558878810 May 30  2018  Anaconda2-5.1.0-Linux-x86_64.sh
-rw-rw-r-- 1 user user 690850711 Jul 13  2022  Anaconda3-2022.05-Linux-x86_64.sh
-rw-rw-r-- 1 user user 577996269 May 30  2018  Anaconda3-5.1.0-Linux-x86_64.sh
drwxrwxr-x 2 user user      4096 Aug 23 00:53  chromedriver_linux64
-rw-rw-r-- 1 user user   7067070 Aug 23 00:14  chromedriver_linux64.zip
drwxr-xr-x 2 user user      4096 May 30  2018  codeblocks
-rw-rw-r-- 1 user user  89863696 Aug 23 00:56 'google-chrome-stable_current_amd64 (1).deb'
-rw-rw-r-- 1 user user  89863696 Aug 23 00:23  google-chrome-stable_current_amd64.deb
-rw-rw-r-- 1 user user 305557504 May 30  2018  jdk-8u171-nb-8_2-linux-x64.sh
-rw-rw-r-- 1 user user 223882240 May 30  2018  netbeans-8.2-linux.sh
```

> -t option sorts in most recently modified 
```
root@ubn-3620:~/Downloads# ls -lt
total 2484376
-rw-rw-r-- 1 user user  89863696 Aug 23 00:56 'google-chrome-stable_current_amd64 (1).deb'
drwxrwxr-x 2 user user      4096 Aug 23 00:53  chromedriver_linux64
-rw-rw-r-- 1 user user  89863696 Aug 23 00:23  google-chrome-stable_current_amd64.deb
-rw-rw-r-- 1 user user   7067070 Aug 23 00:14  chromedriver_linux64.zip
-rw-rw-r-- 1 user user 690850711 Jul 13  2022  Anaconda3-2022.05-Linux-x86_64.sh
drwxr-xr-x 2 user user      4096 May 30  2018  codeblocks
-rw-rw-r-- 1 user user 558878810 May 30  2018  Anaconda2-5.1.0-Linux-x86_64.sh
-rw-rw-r-- 1 user user 577996269 May 30  2018  Anaconda3-5.1.0-Linux-x86_64.sh
-rw-rw-r-- 1 user user 305557504 May 30  2018  jdk-8u171-nb-8_2-linux-x64.sh
-rw-rw-r-- 1 user user 223882240 May 30  2018  netbeans-8.2-linux.sh
```

> --reverse (using long option) 
```
root@ubn-3620:~/Downloads# ls -lt --reverse
total 2484376
-rw-rw-r-- 1 user user 223882240 May 30  2018  netbeans-8.2-linux.sh
-rw-rw-r-- 1 user user 305557504 May 30  2018  jdk-8u171-nb-8_2-linux-x64.sh
-rw-rw-r-- 1 user user 577996269 May 30  2018  Anaconda3-5.1.0-Linux-x86_64.sh
-rw-rw-r-- 1 user user 558878810 May 30  2018  Anaconda2-5.1.0-Linux-x86_64.sh
drwxr-xr-x 2 user user      4096 May 30  2018  codeblocks
-rw-rw-r-- 1 user user 690850711 Jul 13  2022  Anaconda3-2022.05-Linux-x86_64.sh
-rw-rw-r-- 1 user user   7067070 Aug 23 00:14  chromedriver_linux64.zip
-rw-rw-r-- 1 user user  89863696 Aug 23 00:23  google-chrome-stable_current_amd64.deb
drwxrwxr-x 2 user user      4096 Aug 23 00:53  chromedriver_linux64
-rw-rw-r-- 1 user user  89863696 Aug 23 00:56 'google-chrome-stable_current_amd64 (1).deb'
```

| Option | Long option | Description | 
| -a | --all | List all files, even those with names that begin with a period, which are normally not listed (that is, hidden). | 

```
-A --almost-all Like the -a option except it does not list . (current directory) and .. (parent directory).
-d --directory Ordinarily, if a directory is specified, ls will list the
contents of the directory, not the directory itself. Use this
option in conjunction with the -l option to see details
about the directory rather than its contents.
-F --classify This option will append an indicator character to the
end of each listed name. For example, it will append a
forward slash (/) if the name is a directory.
-h --human-readable In long format listings, display file sizes in humanreadable format rather than in bytes.
-l Display results in long format.
-r --reverse Display the results in reverse order. Normally, ls displays its results in ascending alphabetical order.
-S Sort results by file size.
-t Sort by modification time.
```

#### Chapter 4:
#### Chapter 5:
#### Chapter 6:
#### Chapter 7:
#### Chapter 8:
#### Chapter 9:
#### Chapter 10:
 
