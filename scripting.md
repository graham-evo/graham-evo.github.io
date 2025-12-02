---
title:  
layout: page
permalink: /coding_tutorials/scripting/
nav_exclude: true
---

## Shell Scripts
**Shell Scripts** are plain text files that contain a series of commands that can be run automatically by an *interpreter*. A Bash script is a script interpreted by the unix-shell interpreter whereas a Batch script is a script interpreted by the cmd.exe Windows interpeter. There are many different interpreters that interpret code. For example, Python code is interpreted by the python interpreter. Some languages are not read by an interpreter but rather *compiled* directly to machine code (i.e. C/C++).

On unix-based systems the go to batch script is a Bash script which typically has the file extension `.sh`. We can open the terminal with `⌘ + Space`, typing *terminal*, and pressing `enter`.
To create a new file, we can type `touch` followed by the filename


Some basic shell commands that everyone should get used to are:
-   `ls` --> lists the contents of a directory
-   `cd` --> changes directories
-   `pwd` --> prints working directory
-   `mkdir` --> makes a directory
-   `cp` --> copy a file or directory (`-r`)
-   `mv` --> move a file or directory
Keep in mind that the term *directory* is synonymous with folder.

Each shell command and often commands associated with other programs will have a manual page or a help page accessible through the terminal. For example, the manual for `ls` can be viewed using `man ls`. This manual shows all the *options* associated with each shell command, which can be called using *short* or *long* syntax. Some commands only have one or the other. `ls` only has short syntax options, which include a single hyphen (`-`) versus long format syntax which include two hyphens (`--`) and are often followed by full statements rather than abbreviations associated with short syntax option calls.

For example, typing `ls` prints
``` bash
(base) MacBook-Pro-551:~ grahammclaughlin$ ls
Documents
Desktop
Downloads
```
whereas `ls -h -a` prints *all* files including hidden ones beginning with `.`
``` bash
(base) MacBook-Pro-551:~ grahammclaughlin$ ls -a
.
..
.bash_history
.bash_profile
.bash_sessions
Documents
Desktop
Downloads
```




