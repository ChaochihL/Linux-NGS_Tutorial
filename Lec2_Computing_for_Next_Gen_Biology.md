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

***

<!-- Exercises color scheme -->
<!-- background: #063852 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# Exercise 3.2: Viewing FASTQ File

Now that we have a directory called `bds-files` in ~/Itasca with Vince's dataset, go into `bds-files` and see what's there (hint: use `cd` command).

We will use the `find` command we used in Lec 1 to find which directory the `.fastq` files are located in. Don't remember the exact command? Use a combination of `history` and `grep` commands to find it

We will search through our entire history with `history` and pipe the STDOUT to `grep`.

```
history | grep '*.fasta'
```

Once we find the command, we will change the `*.fasta` part to `*.fastq`

***

<!-- Exercises color scheme -->
<!-- background: #063852 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# FASTQ File Format

This file format is used to store high-throughput sequencing data, reported with a per-base quality score indicating confidence of each base call.

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

# BED/GFF3 Format

Describe regions or intervals.

Must be paired with a reference.

BED: usually just intervals. Useful for masking or extracting pieces of sequence.
- BED12 format is the more modern version and more descriptive

GFF3: intervals and qualifiers. Used in genome browsers to list mRNA, CDS, UTR, repeat regions, restriction sites...

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# BED file format

Example BED file from [Vince's Chapter 11](https://github.com/vsbuffalo/bds-files/blob/master/chapter-11-alignment/USH2A_exons.bed)

```
1	216596556	216596738
1	216595194	216595882
1	216591856	216592021
1	216538295	216538427
1	216500933	216500996
1	216498647	216498941
1	216497510	216497694
1	216496816	216497037
1	216495225	216495318
1	216465517	216465712
1	216462622	216462752
1	216424245	216424440
1	216419927	216420568
1	216405295	216405478
1	216390729	216390892
1	216380615	216380773
1	216372969	216373463
1	216371657	216371926
```

***

<!-- background: #000100 -->
<!-- color: #F1F1F2-->
<!-- font: metronova -->

# GFF File Format

Columns in `Morex_Annotations_WithPhase.gff`:
1. Seqname: name of chromosome
2. Source: name of program that generated feature
3. Feature type name: i.e. Gene, Variation, Similarity
4. Start position
5. End position
6. Score – floating point value
7. Froward (+) or reverse(-) strand
8. Frame: either 0 (first base of codon),1 (2nd base of codon) or 2
9. Additional info about each feature

Example GFF file

```

```


