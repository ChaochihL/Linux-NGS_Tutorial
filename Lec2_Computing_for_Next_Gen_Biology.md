<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Computing for Next Generation Biology

## [Thomas Girke Tutorial](http://manuals.bioinformatics.ucr.edu/home/linux-basics)

#### Lab: [Peter Morrell](https://github.com/MorrellLAB)

#### Chaochih Liu

##### August 14, 2015

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Novel Problems in Biology

1. Hundreds of gigabytes of data
2. Computationally-intense algorithms
3. Solution: Use a super computer!

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# MSI Quirks

### Module system
- Local user: account on your computer
- login.msi.umn.edu: any of the MSI login nodes
- resource.msi.umn.edu: any one of the systems behind MSI login nodes
    - i.e. Lab, Mesabi, etc.

### MSI queuing system (PBS Queue)
- Called PBS (Portable Batch System)
- Create PBS job scripts to submit a job
- Use `qsub scriptname` to submit a job
- Use `qstat –u username` to check on all jobs you have submitted
- Use `qdel jobIDnumber` to cancel a submitted job

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Scripts

You will likely find yourself working in a UNIX-like environment (MSI runs Linux)
- Specific, optimized tools
- Easy-to-parse text files
- Pipeline-like flow of data between tools

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# General Workflow

insert image later

Tools are given at the end of slides.

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Mapping and Alignment

insert image later

This figure was from GATK Broad Institute.

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# File Formats

Most are plain text

Well-defined and easy to parse
- Pre-built tools for parsing (SAMTools, VCF Tools, etc...)

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# FASTQ File Format

Four Fields

insert image later

- <font color="blue"> Name (description line) - starts with `@` </font>
- <font color="green"> Sequence data </font>
- <font color="red"> End of sequence </font>
- <font color="orange"> Quality data - same length as sequence </font>

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Git

Version Control System
- Keep track of changes
- Use specific version of code
- Free software

Command-line tool or GUI application

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Git Vs. MS Word

insert images later

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Intro to GitHub

Collaboration
- Review changes
- Comment on code
- Report issues

Sharing of code
- Get feedback

User friendliness
- Web-based graphical interface
- READMEs and Wiki pages

An account is not necessary to view and download public repositories.

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Vince Buffalo's *Bioinformatic Data Skills* Book

Insert image later

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Useful Git Commands

**Create Repositories**
- To obtain a repository from and existing URL

```
git clone [url]
```

- To create a new repository

```
git init [project_name]
```

**Synchronize Changes**
- Downloads history and updates changes
- You must be in the repository before you run this command

```
git pull
```

- Uploads all local changes (use all three commands in order)
- You add the change, commit the change, and push the change

```
git add
git commit -m "commit message"
git push
```

For more git commands, refer to [Git Cheat Sheet](https://services.github.com/kit/downloads/github-git-cheat-sheet.pdf)

***

<!-- Exercises color scheme -->
<!-- background: #063852 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Exercise 3.1: Downloading Dataset from GitHub

Dataset used: from Vince Buffalo's book *Bioinformatics Data Skills" - Chapters 10 and 11

[Vince Buffalo's GitHub Page](https://github.com/vsbuffalo) is open to the public
- Creating an account is free but not necessary for *today*

Use the following git commands in terminal:

```
#   Make sure you are in the directory ~/Itasca
#   To download files in Vince's GitHub repository (this may take a couple minutes)
git clone https://github.com/vsbuffalo/bds-files.git
```

Now check to make sure it has been downloaded to `~/Itasca`
