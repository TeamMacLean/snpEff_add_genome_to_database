## README

Most of the genomes that scientists are researching are already add to snpEff database. However, you may want to add your own genome assembly to the database. Here, I am going to show you how to add your genome assembly to snpEff database.

## How to add a genome to snpEFf database with gff annotation file

Let's say you want to add genome guy11 to the database

1) create a folder for guy11 in the path /tsl/software/testing/snpEff/4.2/src/snpEff/data. Now we have a folder /tsl/software/testing/snpEff/4.2/src/snpEff/data/guy11
2) add guy11 genome/assembly to this path and name it as  sequences.fa. Now we have a file /tsl/software/testing/snpEff/4.2/src/snpEff/data/guy11/sequences.fa
3) add gff3 annotation for guy11 genome in this path and name it as genes.gff. Now we have a file /tsl/software/testing/snpEff/4.2/src/snpEff/data/guy11/genes.gff
4) [optional] If you have protein sequences for guy11, add the protein sequences to the path and name it as protein.fa.  Now we have a file /tsl/software/testing/snpEff/4.2/src/snpEff/data/guy11/protein.fa
5) Open and Edit the file : /tsl/software/testing/snpEff/4.2/x86_64/snpEff.config , and add the following lines. Don't paste these lines that will mess up other entries.
```
# Guy11 : Magnaporthe oryzae strain guy11
guy11.genome : guy11
guy.reference : /tsl/software/testing/snpEff/4.2/src/snpEff/data/guy11
```
6) Run the commands :
```
source snpEff-4.2
source java-11.0.7

snpEff build -gff3 -v guy11
```

I have build the guy11 genome. The log output from the build command is in the file log.txt
