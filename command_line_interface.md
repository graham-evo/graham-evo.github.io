---
title:  
layout: page
permalink: /coding_tutorials/cli/
nav_exclude: true
---

## Interfacing with the Computer
**Command-line interpreters, CLIs** are often referred to as 'shells'. These are computer programs that allow the user to directly interact with the computer. These programs are run inside a **terminal**, which creates a text display allowing for the direct input of commands.

On **Linux** and **MacOS** systems the most popular CLIs are unix-based `zsh` and `bash`, which come pre-installed on most Apple computers and are accessible through the **Terminal** application. On MacOS you can open any application - in this case terminal - with `⌘ + Space`, typing *terminal*, and pressing `enter`.
On **Windows** systems, `PowerShell` or `cmd.exe`, with the latter being the legacy application and the former being more widely used. On Windows systems you can open any application - in this case `cmd.exe` - with `win(⊞) + R`, typing *cmd*, and pressing `enter`.

Once inside the terminal, basic file operations can be more easily and quickly executed compared to using a **Graphical User Interface (GUI)**. P.S. I will mostly discuss the details of unix-based CLI commands and behaviors since I am a MacOS user and since most remote servers are run on unix.

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




