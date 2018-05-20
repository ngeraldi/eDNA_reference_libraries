# Training_datasets
Training datasets for dada2 and insect pipelines, see rep for available primers

The rbcl data base was created by searching the ncbi web site (see R code) on 19 May 2018 using the 
rentrez and insect packages with the following terms "(rbcl[All Fields] AND (Embryophyta[Organism] OR Plants[All Fields]) 
AND 00000000001[SLEN] : 00000010000[SLEN]) NOT (Metazoa[Organism] OR animals[All Fields]))".  
Sequence size was limited to <10,000 bp. Attributes of the fasta are formatted following the DADA2 protocal with 
the following taxonomy which will need to be input in DADA2 assigntaxonomy function
c("superkingdom","kingdom","phylum","class","order","family","genus","species")
