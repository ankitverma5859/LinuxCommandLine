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

Starts with -     : Regular File
Starts with d     : Directory
Number            : Number of Hard Links 
Next 3 characters : Access Rights for File Owner
Next 3 characters : Access Rights for the members of files group
Next 3 characters : Access Rights for everyone else

user              : Username of the File's Owner
user              : Name of the group that owns the file
                  : Size of the file in bytes
                  : Last Modified Date
                  : Name of the file.
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
|------- | ------------ | ---------- |
| -a | --all | List all files, even those with names that begin with a period, which are normally not listed (that is, hidden). | 
| -A | --almost-all | Like the -a option except it does not list . (current directory) and .. (parent directory). |
| -d | --directory | Ordinarily, if a directory is specified, ls will list the contents of the directory, not the directory itself. Use this option in conjunction with the -l option to see details about the directory rather than its contents.|
| -F | --classify | This option will append an indicator character to the end of each listed name. For example, it will append a forward slash (/) if the name is a directory.|
| -h | --human-readable | In long format listings, display file sizes in humanreadable format rather than in bytes.|
|-l | | Display results in long format.|
|-r | --reverse | Display the results in reverse order. Normally, ls displays its results in ascending alphabetical order.|
|-S | | Sort results by file size.|
|-t | | Sort by modification time.|

> less
```
less filename
UP arrow    : 1 line up
Down arrow  : 1 line down
B           : One Page up
SPACE       : One Page down
G           : End of the doc
g           : First Page of the doc
/characters : Search
n           : Next Occurance of the above 
q           : Quit
```


##### Soft Links
- Soft Links / Symbolic Links / Symlinks are required in a following scenario.
- Suppose there is a shared resource of some kind stored in a file called foo.
- Now, if the foo is updated to a new version called foo_2.6, all the programs using this shared resource needs to be updated with the filename.
- Here, soft links comes in to picture. We create a symbolic link called foo and point it to foo_2.6. All the programs refer to foo to execute. Since, foo is pointing to foo_2.6 it will be executed.
- During the update/downgrade of the version we just update the symbolic link of the foo, and thats it.

#### Chapter 4: Manipulating Files and Directories

> COPY
```
cp source destination
```

> Wildcards

| Wildcard | Meaning |
| -------- | ------- |
| * | Matches any characters |
| ? | Matches a single character |
| [characters] | Matchers any character that is member of the set of characters |
| [!characters] | Matches any character that is not a member of the set of characters |
| [:class:] | Matches any character that is member of the specified class |

> Classes

| Character class | Meaning | 
| --------------- | ------- |
| [:alnum:] | Matches any alphanumeric character |
| [:alpha:] | Matches any alphabetic character |
| [:digit:] | Matches any numeral |
| [:lower:] | Matches any lowercase letter |
| [:upper:] | Matches any uppercase letter | 

> Examples 

|Pattern | Matches |
| ------ | ------- |
| * | All files |
| g* | Any file beginning with g |
| b*.txt | Any file beginning with b followed by any characters and ending with .txt |
| Data??? | Any file beginning with Data followed by exactly three characters |
| [abc]* | Any file beginning with either an a, a b, or a c |
| BACKUP.[0-9][0-9][0-9] | Any file beginning with BACKUP. followed by exactly three numerals |
| [[:upper:]]* | Any file beginning with an uppercase letter |
| [![:digit:]]* | Any file not beginning with a numeral |
| *[[:lower:]123] | Any file ending |

> cp Options

| Option | Long Option | Meaning |
| ------ | ----------- | ------- |
|-a | --archive | Copy the files and directories and all of their attributes, including ownerships and permissions. Normally, copies take on the default attributes of the user performing the copy. |
| -i | --interactive | Before overwriting an existing file, prompt the user for confirmation. If this option is not specified, cp will silently (meaning there will be no warning) overwrite files. |
| -r | --recursive | Recursively copy directories and their contents. This option (or the -a option) is required when copying directories. |
| -u | --update | When copying files from one directory to another, only copy files that either don’t exist or are newer than the existing corresponding files in the destination directory. This is useful when copying large numbers of files as it skips files that don’t need to be copied. |
| -v | --verbose | Display informative messages as the copy is performed. |

> Make Directory (mkdir)
```
mkdir directory...
mkdir dir1
mkdir dir1 dir2 dir3
```
- (...) three dots means that the command can be repeated

> Move (mv)
```
mv source destination
```

> Remove (rm)
```
rm item...
```

> Link (ln)

- Suppose you have a file in dir1 and you want this same file in dir2 as well. 
- Option 1: You can copy the file from dir1 to dir2.
- Option 2: You can create a link/reference to the file in dir1 from dir2. This is useful when you do not want to create a replica of the file. It saves memory. Also, if you make change at one place, it will be reflected at all the places.

> Hard Link 
```
ln item link
```

- With -i option we can see the inode number which confirms if two file are linked.
- Here, 3148780 is inode number of files fun.txt dir1/fun_1.txt and dir2/fun_2.txt
- We can also observe, the number of hardlinks is 3.

```
root@ubn-3620:~/Documents/arena# ln fun.txt dir1/fun_1.txt
root@ubn-3620:~/Documents/arena# ln fun.txt dir2/fun_2.txt

root@ubn-3620:~/Documents/arena# ls -li . dir1 dir2
.:
total 12
3162155 drwxr-xr-x 2 root root 4096 Feb  6 10:44 dir1
3162156 drwxr-xr-x 2 root root 4096 Feb  6 10:45 dir2
3148780 -rw-r--r-- ***3*** root root   18 Feb  6 10:44 fun.txt

dir1:
total 4
3148780 -rw-r--r-- 3 root root 18 Feb  6 10:44 fun_1.txt

dir2:
total 4
3148780 -rw-r--r-- 3 root root 18 Feb  6 10:44 fun_2.txt
```

- There are few limitations of hard links. 
- A hard link cannot reference a file that is outside its file system i.e a link cannot reference a file that is not on the same disk partition.
- A hard link may not reference a directory.


> Soft Link
- The limitations of hard links are oversome with soft links.
- Just add -s option to it. 

```
ln -s item link
```

```
root@ubn-3620:~/Documents/arena# ln -s fun.txt dir1/fun_1.txt
root@ubn-3620:~/Documents/arena# cd dir1
root@ubn-3620:~/Documents/arena/dir1# ls -l
total 0
lrwxrwxrwx 1 root root 7 Feb  6 10:56 fun_1.txt -> fun.txt
```

- With -l optoin of ls, we can observe the soft link ***fun_1.txt -> fun.txt***

#### Chapter 5: Working with Commands

>

#### Chapter 6:
#### Chapter 7:
#### Chapter 8:
#### Chapter 9:
#### Chapter 10:
 
