# Lab_6_comparative_genomics_1

## Introduction
This week in lab, we will find the gene **PGM1** in your genome annotations. We will be using Blast on the cluster. 
The end result will be a fasta protein sequence file with your ortholog(s) in it.

This week, you **will be writing your own commands**. This may take some trial and error. Don't forget to look at any files you produce. 

## Step 1 Setup

To set up your lab_6 folder you will need to add just three files.

Create a new lab_6 folder and then add the following files to that folder using `cp`
- pgm1 nucleotide fasta file `/projects/class/binf3101_001/pgm1/pgm1.fasta`
- Your nucleotide CDS file that should be in your lab_5 folder example: SRR6475892.cds.fasta
- Your translated protein file that should be in your lab_5 folder example: SRR6475892.prot.fasta

## Step 2 blastx command

You will be using **blastx** to search your protein coding sequences with the nucleotide sequence of PGM1. 

You can read all about the blast command line options here: https://www.ncbi.nlm.nih.gov/books/NBK279684/

The entire blast suite is already installed on the cluster. To activate it, you use

```bash
module load blast
```


**NOTE** The results will print to your screen when you use any of the blast commands in the command line. If you want to save the results to a file you can add a `>` to the end of your command and that will direct the output to a new file. For example

```bash
blastx options > results.txt
```

Instead of printing the results to the screen, they will now be saved in the results.txt file that you can open! 

Draft your blastx command. Execute the command and look at the results. 


## Step 3 Analyze your blast output



