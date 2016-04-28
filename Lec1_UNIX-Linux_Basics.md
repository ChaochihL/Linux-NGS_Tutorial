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

The :arrow_up: and :arrow_down: arrows scroll through command history 
