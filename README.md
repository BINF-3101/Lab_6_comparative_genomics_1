# Lab_6_comparative_genomics_1
&ensp;
# Outline

[Introduction](#introduction)

[Step 1 Setup](#step-1-setup)

[Step 2 Fix fasta files](#step-2-fix-our-fasta-files)

[Lab Question 1](#lq-1)

[Step 3 blastp](#step-3-blastp-command)

[Step 4 Analyze Blast output](#step-4-analyze-your-blast-output)

[Lab Question 2](#lq-2)

[Lab Question 3](#lq-3)

[Lab Question 4](#lq-4)

[Lab Question 5](#lq-5)

[Step 5 Extract sequences](#step-5-extract-the-sequences)

[Step 6 Pick a metabolic pathway](#step-6-pick-a-metabolic-pathway)

&ensp;
## Introduction
This week in lab, we will find the gene **PGM1** in your genome annotations. We will be using Blast on the cluster. 
The end result will be a fasta protein sequence file with your ortholog(s) in it.

This week, you **will be writing your own commands**. This may take some trial and error. Don't forget to look at any files you produce. 

&ensp;
&ensp;

## Step 1 Setup

To set up your lab_6 folder you will need to add just three files.

Create a new lab_6 folder and then add the following files to that folder using `cp`
- pgm1 nucleotide fasta file `/projects/class/binf3101_001/pgm1/pgm1.fasta`
- Your translated protein file that should be in your lab_5 folder example: SRR6475892.prot.fasta
&ensp;
&ensp;
## Step 2 fix our fasta files

Due to the format of braker many of the coding sequences are reported more than once in our cds.fasta and prot.fasta files. 

To fix this you must complete the following steps. 

```bash
cd lab_6
cp /projects/class/binf3101_001/sequence_cleaner.py .

module load anaconda3

python sequence_cleaner.py SRR0000.prot.fasta

```

This will produce a new file
clear_SRR0000.prot.fasta 


**Use the clear files moving forward**
&ensp;
# LQ 1

How many sequences are in your **clear** prot.fasta file?


&ensp;
&ensp;
## Step 3 blastp command

You will be using **blastp** to search your protein-coding sequences with the protein sequence of PGM1. 

You can read all about the blast command line options here: https://www.ncbi.nlm.nih.gov/books/NBK279684/

The entire blast suite is already installed on the cluster. To activate it, you use

```bash
module load blast
```


**NOTE** The results will print to your screen when you use any of the blast commands in the command line. If you want to save the results to a file you can add a `>` to the end of your command and that will direct the output to a new file. For example

```bash
blastp options > results.txt
```

Instead of printing the results to the screen, they will now be saved in the results.txt file that you can open! 

Draft your blastp command. Execute the command and look at the results. 

&ensp;
&ensp;
## Step 4 Analyze your blast output

Take a look at your blast results. You should **at least 1 significant hit** in your results. Answer the questions below about your blast output
&ensp;
# LQ 2 
How many sequences produced significant alignments to the reference PGM1?
&ensp;
# LQ 3 
What is the E-value associated with your most significant alignment?
&ensp;
# LQ 4 
What is your most significant alignment's % identity to the reference PGM1 sequence?
&ensp;
# LQ 5 
What is the sequence's identifier (or name) producing the most significant alignment?

&ensp;
&ensp;
## Step 5 Extract the sequences
&ensp;
### Step 5a - Create a file with your sequence identifier in it
We want to get the nucleotide and protein sequences of the PGM1 ortholog. We can do this using the sequence identifier. 

We want to add the sequence identifier to a list of genes in a file. To do this we can use the bash command echo. 

```bash
echo "sequence_name_from_blast" > to_get.txt
```

If you look at the to_get.txt file it should contain 1 line with your desired sequence identifier.
&ensp;
### Step 5b - Extract the protein sequence with seqtk

Now we will use the seqtk package to extract our protein sequence. To do this you will execute a command similar to the one below

```bash
module load seqtk

seqtk subseq clear_SRR0000.prot.fasta to_get.txt > SRR00000.pgm1.fasta
```
&ensp;
### Step 5c - Copy your pgm1 file into the class space

Copy your pgm1 fasta file into the shared class directory.

```bash
cp SRR0000.pgm1.fasta /projects/class/binf3101_001/pgm1_class_results/.
```
&ensp;
&ensp;

### Step 6 Pick a metabolic pathway

Download the yeast_metabolic_data.xlsx from the Canvas Lab 6 instructions. 

Find your species name on the list. 

Find a substrate that your yeast species grows on that you would like to focus on. 
&ensp;
# LQ 6 
Report the substrate you would like to focus on for Lab 7.











