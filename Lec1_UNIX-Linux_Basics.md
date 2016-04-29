<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Unix/Linux Basics

## [Thomas Girke Tutorial](http://manuals.bioinformatics.ucr.edu/home/linux-basics)

#### Lab: [Peter Morrell](https://github.com/MorrellLAB)

#### Chaochih Liu

##### August 14, 2015

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Learning Outcomes

Using powerful Linux command-line utilities.

Learn commonly used Linux commands.

Servers at the Minnesota Supercomputing Institute (MSI) run Linux

- Need to log-in into the remote Linux shell

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Logging-In

### Mac or LINUX

To log-in to the remote Linux shell, open the terminal and type:

```
ssh <your_username>@<host_name>
```

Where `ssh` stands for secure shell and `host_name` is the remote server's domain name (i.e. login.msi.umn.edu). You will then be asked to enter your password, simply type it and press enter.

The format you will use to log-in to [MSI](https://www.msi.umn.edu/) at the University of Minnesota is:

```
ssh x500@login.msi.umn.edu
```

For the purposes of this tutorial we will only work from Macs, if you have questions on logging in to MSI from a Windows machine, let me know. 

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Why GNU/Linux?

- Software costs $0
- Advanced Multitasking
- Remote tasking (“real networking”)
- Multiuser
- Easy access to programming languages, databases, open-source projects

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Why GNU/Linux?

- Software freedoms
    - Free to use for any purpose
    - Free to study and modify the source code
    - Free to share
    - Free to share modified versions
- No dependence on vendors
- Better performance
- More up-to-date
- Many more reasons…

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Basics

### Things to keep in mind throughout this tutorial

Remember the UNIX/LINUX command  line is case sensitive!

All commands in this manual are printed in gray code boxes.

Commands given in <span style="color:red">red</span> are considered more important for beginners than commands given in <span style="background-color:#F1F1F2"><span style="color:black">black</span></span>.

The hash (pound) sign `#` indicates the start of comments for commands.

The notation `<…>` refers to variables and file names that need to be specified by the user. The symbols `<` and `>` need to be excluded.

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Unix/Linux Help

One very useful resource is knowing where to get help. You don't have to memorize every single UNIX/Linux command, but you do need to know where to get help.

You can look up what any UNIX/Linux command does by using the `man <something>` command. To exit general help, press the `q` key.

For example, let's look at what the `wc` command does:

```
man wc   # manual on program 'word count' wc
```

To get a shorter version of help of `wc` type:

```
wc --help   # short help on wc
```

Online help: Google

Go to [linuxconfig.org](https://linuxconfig.org/linux-commands) for universally available Linux commands with detailed examples and explanations.

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Orientation

To view which directory you are in use:

```
pwd     # Get full path of present working directory
```

To view the present working directory use:

```
ls      # content of present working directory
ls -l   # ls plus additional info on files and directories
ls -t   # list files in chronological order
ls -lh  # view size of files in present working directory 
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Orientation

To change directories use:

```
cd <dir_name>       # switch into specified directory
cd                  # brings you to highest level of your home directory
cd ..               # moves one directory up
cd ../../           # moves two directories up (and so on)
```

The tilde symbol `~` gets interpreted as the path to your home directory. This will work the same anywhere on the command line:

```
echo ~      # view the full (complete) path of your home
find ~      # list all your files (including everything in sub-directories)
ls ~        # list the top level files of your home directory
du -sh ~/*  # calculate the file sizes in your home directory
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Exercise 1.1: Files and Directories

Here are some basic commands before we jump into the exercise:

```
mkdir <dir_name>    # creates specified directory
rmdir <dir_name>    # removes empty directory
rm <file_name>      # removes file
rm -r <dir_name>    # removes directory including its contents but asks for confirmation
rm -rf <dir_name>   # removes directory including its contents with confirmation off

cp <name> <path>    # copy file/directory to specified location (-r to include content in dir)
mv <name1> <name2>  # renames directories or files
mv <name> <path>    # moves file/directory to specified location
```

For the exercise:

Make a directory called **GitHub** with the `mkdir` command:

```
mkdir GitHub
```

Go into your `GitHub` directory with the `cd` command

```
cd GitHub
``` 

Make another test directory called `test` within your `GitHub` directory

```
mkdir test
```

Now we will remove the directory called `test` with the `rm` command

```
rm -rf test/
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Copy and paste

The methods will differ depending on where you are:

In a **command line** environment:
- Cut last word with `Ctrl+w`
- Paste with `Ctrl+y`

In a non-command line **desktop** environment:
- Copy with `Ctrl+c`
- Paste with `Ctrl+v`

Command line <-> **desktop** exchange:
- Copy text out of the **command line** and into the **desktop** with `Shift+Ctrl+c` or `Apple+c`
- Paste text from the **desktop** into the **command line** with `Shift+Ctrl+v` or `Apple+v`

Note: These shortcuts are the defaults but can be changed and customized to the user's preferences.

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Handy Shortcuts

#### Anywhere in Command Line:

The :arrow_up: and :arrow_down: arrows scroll through command history.

Typing `history` will show all the commands you have used recently.

#### Auto Completion:

Typing the beginning of something followed by `TAB` will complete the program_path/file_name.

`<something-incomplete> TAB` 

#### Taking control over the cursor (the pointer on the command line):

- :star: `Ctrl+a` takes cursor to the beginning of the command line
- :star: `Ctrl+e` takes cursor to the end of the command line
- `Ctrl+w` cuts the last word
- `Ctrl+k` cuts to the end of the line
- `Ctrl+y` paste content that was cut earlier (by `Ctrl+w` or `Ctrl+k`)

#### When specifying file names:

- `.` (dot) refers to the present working directory
- `~` (Tilda) or `~/` refers to the user's home directory 

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Finding Files in Directories and Applications

#### Here are some important commands to know:

```
find -name "*pattern*"              # searches for *pattern* in and below current directory
find /usr/local -name "*blast*"     # finds file names *blast* in specified directory
find /usr/local -iname "*blast*"    # Same as above, but case insensitive
```

#### Here are some additional useful arguments that would be good to know exist:

- `-user <user name>`
- `-group <group name>`
- `-ctime <number of days ago changed>`

```
find ~ -type f -mtime -2        # finds all files you have modified in the last two days
locate <pattern>                # finds files and directories that are written into update file
which <application_name>        # location of application
whereis <application_name>      # searches for executeables in set of directories
dpkg -l | grep mypattern        # find Debian packages and refine search with grep pattern
```

#### Example of a `find` command we will be using frequently later on today

```
find `pwd` -name "filename" | sort
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Finding Things in Files

#### Grep

:star: `grep` searches **within files** whereas `find` searches **directories**

```
grep pattern file           # provides lines in 'file' where pattern 'appears'
                            # if pattern is shell function use single quotes: '>'
                            
grep -H pattern             # -H prints out file name in front of pattern

grep 'pattern' file | wc    # pipes lines with pattern into word count 'wc'
                            # wc arguments: 
                            #   -c: show only bytes 
                            #   -w: show only words
                            #   -l: show only lines
                            # help on regular expressions: 
                            #   $ man 7 regex
                            #   man perlre    
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Permissions and Ownership

#### List directories and files

```
ls -al  # shows something like this for each file/dir:
        #   drwxrwxrwx
        # d: directory
        # rwx: read, write, execute
        # first triplet: user permissions (u)
        # second triplet: group permissions (g)
        # third triplet: world permissions (o)        
```

#### Assign write and execute permissions to user and group

```
chmod ug+rx my_file
```

#### To remove all permissions from all three user groups

```
chmod ugo-rwx my_file      # '+' adds permissions
                           # '-' removes permissions
                           # '=' causes them to be the only permissions the file has
```

#### Change ownership

```
chown <user> <file or dir>          # change user ownership
chgrp <group> <file or dir>         # changes group ownership
chown <user>:<group> <file or dir>  # changes user & group ownership
```

***

<!-- background: #063852 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Exercise 1.2: Useful Unix Commands

#### Commands that will be used in the exercise:

```
wget ftp://ftp.ncbi.nih...      # download file from web

du -sh              # displays disk space usage of current directory
du -sh *            # displays disk space usage of individual files/directories
du -s * | sort -nr  # shows disk space used by different files/directories sorted by size
```

#### Exercise 1.2

You should already be in the directory `GitHub` we created earlier. If not, use `cd` to go into the directory.

```
cd ~/GitHub
```

To download files to the `GitHub` directory, you must have the url of the raw format of the file. Use the command `wget` to download the files. 

You can download files by copying and pasting one url at a time

```
wget https://raw.githubusercontent.com/vsbuffalo/bds-files/master/chapter-07-unix-data-tools/contam.fastq
```

Let's download another file from a different url

```
wget https://raw.githubusercontent.com/vsbuffalo/bds-files/master/chapter-07-unix-data-tools/contaminated.fastq

```

Now we'll download multiple files from different links with `wget`.

Each link must be separated by a space

```
wget https://raw.githubusercontent.com/vsbuffalo/bds-files/master/chapter-03-remedial-unix/tb1-protein.fasta https://raw.githubusercontent.com/vsbuffalo/bds-files/master/chapter-03-remedial-unix/tb1.fasta https://raw.githubusercontent.com/vsbuffalo/bds-files/master/chapter-03-remedial-unix/tga1-protein.fasta
```

To view file sizes, permissions, date, etc. line by line, use the `ls` command. `-l` means use long listing format and `-h` will print sizes of files in human readable format

```
ls -lh
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# STDIN, STDOUT, and STDERR

By default, UNIX commands read from **standard input (STDIN)** and send their output to **standard out (STDOUT)**.

#### Example: STDIN and STDOUT

This will take the input of a program and output it to be written to a file:

```
ls -l               # lists (outputs) files in long listing format

ls -l > ls-l.txt    # takes output from above and inputs it to a file called 'ls-l.txt'
```

Note: When creating new files, it is easiest to avoid having spaces between names. Use `_` or `-` as spaces instead.

#### Example: STDERR

STDERR are error messages that output to the screen.

This will output an error message to the screen:

```
grep da * 2
```

For more examples, see [LINUX HOWTOs](http://www.tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-3.html)

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Redirections

Before we jump into redirections, I would like to review **wildcards**. 
- Wildcards are denoted by `*` and it is used to specify many files (I'll discuss more details about this later and show an example). 
- A few examples of formats are: 
    - `<beginning-of-filename>*`
    - `*<end-of-filename>`
    - `*<middle-of-filename>*`

Now, we'll go back to redirections.

The following commands are redirections:

```
ls > file               # stores ls output into specified file
command < my_file       # uses file after '<' as STDIN
command >> my_file      # appends output of one command to file (will not overwrite file with same filename)
```


