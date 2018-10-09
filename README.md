# Training_datasets
Training datasets for dada2 and insect pipelines, see rep for available primers

####################################################
####################################################
####################################################

DADA2

Attributes of the fasta are formatted following the DADA2 protocal with 
the following taxonomy which will need to be input in DADA2 assigntaxonomy function
c("superkingdom","kingdom","phylum","class","order","family","genus","species")

To include more sequences in the databases, sequences with either the forward or the reverse primers were kept.
####################################################

rbcl mini (F52/R193)  (Little et al. 2014)

The rbcl data base was created by searching the ncbi web site (see R code) on 19 May 2018 using the 
rentrez and insect packages with the following terms "(rbcl[All Fields] AND (Embryophyta[Organism] OR Plants[All Fields]) 
AND 00000000001[SLEN] : 00000010000[SLEN]) NOT (Metazoa[Organism] OR animals[All Fields]))".  
Sequence size was limited to <10,000 bp. 

All sequences from search

https://www.dropbox.com/s/g4ldcm5q0wen0qv/rbcl_embry_plants_1_10k__cut.fasta?dl=0


only sequences that passed trimmedf (function in insect package with default arguments)

https://www.dropbox.com/s/jvk0f3khkry552q/rbcl_embry_plants_1_10k_dada2_rbclmini_insect_trim.fasta?dl=0

####################################################

CO1 (mlCOIintF and jgHCO2198)  (Leray et al. 2013)

Database was created from Porter and Hajibabaei (2018). Dataset was downloaded from https://github.com/terrimporter/CO1Classifier in version 3 in June 2018. Names were changed for DADA2 format. 

*I would recommend 60% idendity match, based on Porter and Hajibabaei (2017).

Note: An alternative would be to create database from midori database (http://www.reference-midori.info/index.html) from Midori-unique version 20180221 (Machida et al. 2017). 


All sequences from database (this seems to identify more taxa than when cut to primers, 1.28 million sequences)

https://www.dropbox.com/s/51n3pjf40w8sjrz/port_haj_dada_name.fasta?dl=0

Sequences that passed cutadapt and between 100 and 500bp (975080 sequences)

https://www.dropbox.com/s/t0tg148ftyjnpty/port_haj_dada_name_cut_between100and500bp.fasta?dl=0

####################################################

Euka02 primer (Taberlet 2018)

Sequences from Silva database (SILVA_132_SSURef_Nr99_tax_silva_trunc) that passed trimmedf (function in insect package with default arguments) with Euka02 primers.
Todo: check 2 warnings, doen't affect assigntaxonomy.

https://www.dropbox.com/s/tubwo8wpfgawf0l/SILVA_132_SSURef_Nr99_tax_silva_DNA_insect_euka02.fasta?dl=0
