# Training_datasets
Training datasets for dada2 and insect pipelines, see rep for available primers

####################################################
####################################################
####################################################

Attributes of the fasta are formatted following the DADA2 protocal with 
the following taxonomy which will need to be input in DADA2 assigntaxonomy function
c("superkingdom","kingdom","phylum","class","order","family","genus","species")

Format of attributes of fasta for insect have accession|taxaID, then are put in tree formate with learn().

To include more sequences in the databases, sequences with either the forward or the reverse primers were kept.
####################################################

rbcl mini (F52/R193)  (Little et al. 2014)

The rbcl data base was created by searching the ncbi web site (see R code) on 4 Nov. 2018 using the 
rentrez, taxonomizr, and insect packages with the following terms "(rbcl[All Fields] AND ((Embryophyta[Organism] OR Plants[All Fields] OR Chlorophyta[Organism] OR Phaeophyceae[Organism] OR Rhodophyta[Organism]) AND 00000000001[SLEN] : 00000010000[SLEN]) NOT (Metazoa[Organism] OR animals[All Fields]))".  
Sequence size was limited to <10,000 bp. 

All sequences from search (222,173 sequences)

fasta: insect format

https://www.dropbox.com/s/b04s8opfcz1zgs2/ncbi_rbcl_all_insect_names.fasta?dl=0


only sequences that passed trimmedf (function in insect package with default arguments)

Fasta: DADA2 fomrat

https://www.dropbox.com/s/1d2xug13vxcnsa2/ncbi_rbcl_virtualPCR_rbclmini_dada_names.fasta?dl=0

Fasta: Insect format

https://www.dropbox.com/s/xarr4uf4u1bgkqe/ncbi_rbcl_virtualPCR_rbclmini_insect_names.fasta?dl=0

rds: Insect trained tree data

https://www.dropbox.com/s/05067kqwxlurme0/minirbcl_learn.rds?dl=0


####################################################

CO1 (mlCOIintF and jgHCO2198)  (Leray et al. 2013)

Database was created from Porter and Hajibabaei (2018). Dataset was downloaded from https://github.com/terrimporter/CO1Classifier in version 3 in June 2018. Names were changed for DADA2 format. 

*I would recommend 60% idendity match, based on Porter and Hajibabaei (2017).

Note: An alternative would be to create database from midori database (http://www.reference-midori.info/index.html) from Midori-unique version 20180221 (Machida et al. 2017). 


All sequences from database (this seems to identify more taxa than when cut to primers, 1.28 million sequences)

fasta: dada2 formate

https://www.dropbox.com/s/51n3pjf40w8sjrz/port_haj_dada_name.fasta?dl=0

Sequences that passed cutadapt and between 100 and 500bp (975080 sequences)

fasta: data2 foramt

https://www.dropbox.com/s/t0tg148ftyjnpty/port_haj_dada_name_cut_between100and500bp.fasta?dl=0

rds: insect trained tree is avaialble at the insect github site

https://github.com/shaunpwilkinson/insect

####################################################

Euka02 primer (Taberlet 2018)

Sequences from Silva database (SILVA_132_SSURef_Nr99_tax_silva_trunc) that passed trimmedf (function in insect package with default arguments) with Euka02 primers.
Todo: check 2 warnings, doen't affect assigntaxonomy.

Fasta: DADA2 format
https://www.dropbox.com/s/sxmq3s03ppat3c9/SILVA_132_SSURef_Nr99_tax_silva_trunc_DNA_trimmed_euka02_dada_names.fasta?dl=0

rds: Insect trained dataset
https://www.dropbox.com/s/dw43l3qebtvwuuy/euka02_learn.rds?dl=0


