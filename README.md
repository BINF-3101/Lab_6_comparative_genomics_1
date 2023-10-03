# Lab_6_comparative_genomics_1

## Introduction
This week in lab, we will find the gene **PGM1** in your genome annotations. We will be using Blast on the cluster. 
The end result will be a fasta protein sequence file with your ortholog(s) in it.

This week, you **will be writing your own commands**. This may take some trial and error. Don't forget to look at any files you produce. 

## Step 1 Setup

To set up your lab_6 folder you will need to add just three files.

Create a new lab_6 folder and then add the following files to that folder using `cp`
- pgm1 nucleotide fasta file `/projects/class/binf3101_001/pgm1/pgm1.fasta`
- Your translated protein file that should be in your lab_5 folder example: SRR6475892.prot.fasta

## Step 3 fix our fasta files

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

# LQ 1

How many sequences are in your **clear** prot.fasta file?



## Step 3 blastx command

You will be using **blastx** to search your protein-coding sequences with the nucleotide sequence of PGM1. 

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

Take a look at your blast results. You should **at least 1 significant hit** in your results. Answer the questions below about your blast output

# LQ 2 
How many sequences produced significant alignments to the reference PGM1?

# LQ 3 
What is the E-value associated with your most significant alignment?

# LQ 4 
What is your most significant alignment's % identity to the reference PGM1 sequence?

# LQ 5 
What is the sequence's identifier (or name) producing the most significant alignment?


## Step 4 Extract the sequences

### Step 4a - Create a file with your sequence identifier in it
We want to get the nucleotide and protein sequences of the PGM1 ortholog. We can do this using the sequence identifier. 

We want to add the sequence identifier to a list of genes in a file. To do this we can use the bash command echo. 

``bash
echo "sequence_name_from_blast" > to_get.txt
```

If you look at the to_get.txt file it should contain 1 line with your desired sequence identifier.

### Step 4b - Extract the protein sequence with seqtk

Now we will use the seqtk package to extract our protein sequence. To do this you will execute a command similar to the one below

```bash
module load seqtk

seqtk subseq clear_SRR0000.prot.fasta to_get.txt > SRR00000.pgm1.fasta
```

### Step 4c - Copy your pgm1 file into the class space

Copy your pgm1 fasta file into the shared class directory.

```bash
cp SRR0000.pgm1.fasta /projects/class/binf3101_001/pgm1_class_results/.
```

### Step 5 Pick a metabolic pathway

Download the yeast_metabolic_data.xlsx from the Canvas Lab 6 instructions. 

Find your species name on the list. 

Find a substrate that your yeast species grows on that you would like to focus on. 

# LQ 6 
Report the substrate you would like to focus on for Lab 7.











