# Lab_6_comparative_genomics_1
&ensp;
# Outline

[Introduction](#introduction)

[Step 1 Setup](#step-1-setup)

[Step 2 blastp](#step-2-blastp-command)

[Step 3 Analyze Blast output](#step-3-analyze-your-blast-output)

[Lab Question 1](#lq-1)

[Lab Question 2](#lq-2)

[Lab Question 3](#lq-3)

[Lab Question 4](#lq-4)

[Step 4 Extract sequences](#step-4-extract-the-sequences)

[Lab Question 5](#lq-5)

[Lab Question 6](#lq-6)



&ensp;
## Introduction
This week in lab, we will find the gene **Rad53** in your genome annotations. We will be using Blast on the cluster. 
The end result will be a fasta protein sequence file with your ortholog(s) in it.

This week, you **will be writing your own commands**. This may take some trial and error. Don't forget to look at any files you produce. 

&ensp;
&ensp;

## Step 1 Setup

To set up your lab_6 folder you will need to add just three files.

Create a new lab_6 folder and then add the following files to that folder using `cp`
- Rad53 protein fasta file `/projects/class/binf3101_001/lab_6/rad53.fasta`
- Your translated protein file that should be in your lab_5 folder example: SRRXXXX.prot.fa

&ensp;
&ensp;


&ensp;
&ensp;
## Step 2 blastp command

### Step 2a - read about BLASTp
You will be using **blastp** to search your protein-coding sequences with the protein sequence of Rad53. 

You can read all about the blast command line options here: https://www.ncbi.nlm.nih.gov/books/NBK279684/

Here is a tutorial on BLAST on the command line: https://open.oregonstate.education/computationalbiology/chapter/command-line-blast/ 

The entire blast suite is already installed on the cluster. To activate it, you use

```bash
ml blast
```


**NOTE** The results will print to your screen when you use any of the blast commands in the command line. If you want to save the results to a file you can add a `>` to the end of your command and that will direct the output to a new file. For example

```bash
blastp OPTIONS > results.txt
```

Instead of printing the results to the screen, they will now be saved in the results.txt file that you can open! 

### Step 2b - write the blast command!

You will be writing your own blast command. Our goal is to search your protein-coding sequences for the gene Rad53. We have an example Rad53 gene in the Rad53.fasta file. 

Draft your blastp command. Execute the command and look at the results. 

**SET YOUR e-value to 1e-25**

&ensp;
&ensp;
## Step 3 Analyze your blast output

Take a look at your blast results. You should **at least 1 significant hit** in your results. Answer the questions below about your blast output
&ensp;
# LQ 1 
How many sequences produced significant alignments to the reference Rad53?
&ensp;
# LQ 2 
What is the E-value associated with your most significant alignment?
&ensp;
# LQ 3 
What is your most significant alignment's % identity to the reference Rad53 sequence?
&ensp;
# LQ 4
What is the sequence's identifier (or name) producing the most significant alignment?

&ensp;
&ensp;
## Step 4 Extract the sequences
&ensp;
### Step 4a - Create a file with your sequence identifier in it
We want to get the nucleotide and protein sequences of the Rad53 ortholog. We can do this using the sequence identifier. 

We want to add the sequence identifier to a list of genes in a file. To do this we can use the bash command echo. 

```bash
echo "sequence_name_from_blast" > to_get.txt
```

If you look at the to_get.txt file it should contain 1 line with your desired sequence identifier.
&ensp;
### Step 4b - Extract the protein sequence with seqtk

Now we will use the seqtk package to extract our protein sequence. To do this you will execute a command similar to the one below

```bash
module load seqtk

seqtk subseq SRR0000.prot.fasta to_get.txt > SRR00000.Rad53.fasta
```
&ensp;
### Step 5c - Copy your Rad53 file into the class space

Copy your Rad53 fasta file into the shared class directory. _fixed after class on thursday_

```bash
cp SRR0000.Rad53.fasta /projects/class/binf3101_001/Rad53_class_results/.
```
&ensp;
&ensp;

&ensp;
# LQ 5
Take a look at the _Saccharomyces_ genome database https://www.yeastgenome.org/ and search for our gene Rad53

What process is the gene Rad53 involved in?

# LQ 6
What chromosome is Rad53 located on in _Saccharomyces cerevisiae_













