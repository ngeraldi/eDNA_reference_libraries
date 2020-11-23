# Training_datasets
Training datasets for dada2 and insect pipelines, see rep for available primers

Code used to create these is in basic_eDNA_pipline repository-

https://onlinelibrary.wiley.com/doi/abs/10.1111/1755-0998.13018

####################################################
####################################################
####################################################

Attributes of the fasta are formatted following the DADA2 protocal with 
the following taxonomy which will need to be input in DADA2 assigntaxonomy function
c("superkingdom","kingdom","phylum","class","order","family","genus","species")

Format of attributes of fasta for insect have accession|taxaID, then are put in tree formate with learn().

####################################################

rbcl mini (F52/R193)  (Little et al. 2014)
PRIMER1="GTTGGATTCAAAGCTGGTGTTA"
PRIMER2="CVGTCCAMACAGTWGTCCATGT"

The rbcl data base was created by searching the ncbi web site (see R code) on 18 April 2019 using the 
rentrez, taxonomizr, and insect packages with the following terms "(rbcl[All Fields] AND ((Embryophyta[Organism] OR Plants[All Fields] OR Chlorophyta[Organism] OR Phaeophyceae[Organism] OR Rhodophyta[Organism]) AND 00000000001[SLEN] : 00000010000[SLEN]) NOT (Metazoa[Organism] OR animals[All Fields]))".  
Sequence size was limited to <10,000 bp. 

Fasta: DADA2 fomrat

https://www.dropbox.com/s/gnaiz5gawv5nciq/ncbi_rbcl_trimmed_rbclmini_dada2_names.fasta?dl=0

Fasta: Insect format

https://www.dropbox.com/s/qk0x22a3ezvd0tb/ncbi_rbcl_trimmed_rbclmini_insect_names.fasta?dl=0

rds: Insect trained tree data

https://www.dropbox.com/s/6q6f5kbwap3fhut/minirbcl_learn.rds?dl=0


####################################################

CO1 (mlCOIintF and jgHCO2198)  (Leray et al. 2013)
PRIMER1="GGWACWGGWTGAACWGTWTAYCCYCC"
PRIMER2="TANACYTCNGGRTGNCCRAARAAYCA"

Database was created from Porter and Hajibabaei (2018). Dataset was downloaded from https://github.com/terrimporter/CO1Classifier in version 3 in June 2018. Names were changed for DADA2 format. 

*I would recommend 60% idendity match, based on Porter and Hajibabaei (2017).

Note: An alternative would be to create database from midori database (http://www.reference-midori.info/index.html) from Midori-unique version 20180221 (Machida et al. 2017). 


All sequences from database (this seems to identify more taxa than when cut to primers, 1.28 million sequences)

fasta: dada2 format

https://www.dropbox.com/s/51n3pjf40w8sjrz/port_haj_dada_name.fasta?dl=0

Sequences that passed cutadapt and between 100 and 500bp (975080 sequences)

fasta: data2 format

https://www.dropbox.com/s/t0tg148ftyjnpty/port_haj_dada_name_cut_between100and500bp.fasta?dl=0

rds: insect trained tree is avaialble at the insect github site

https://github.com/shaunpwilkinson/insect

####################################################

vertabrate primers  (Riaz et al. 2011)
PRIMER1="ACTGGGATTAGATACCCC"
PRIMER2="TAGAACAGGCTCCTCTAG"

NCBI was searched on November 10 2018 with the following search terms to create initial reference library. These sequenced were then filtered for in silico PCR (using virtualPCR function from insect package) and those that are eukaryotes.

(Vertebrata[Organism] OR Vertebrata[Organism] OR vertebrata[All Fields]) AND (Metazoa[Organism] OR animals[All Fields]) AND 12s[All Fields]) AND 00000000001[SLEN] : 00000010000[SLEN]

Fasta: DADA2 format

https://www.dropbox.com/s/m4185ay0dje8il4/ncbi_12s_euk_only_dada2_virtualPCR.fasta?dl=0

rds: Insect trained dataset (.rds) and fasta used to create tree

https://www.dropbox.com/s/80eqqbaeedenzht/12s_ruiz_learn.rds?dl=0

https://www.dropbox.com/s/10qiuor8uz7be17/ncbi_12s_euk_only_insect_virtualPCR.fasta?dl=0

####################################################

18S rRNA primers

Sequences from Silva database (SILVA_138.1_SSURef_NR99_tax_silva_trunc ; downloaded 23 Nov. 2020 from https://www.arb-silva.de/download/archive/) that passed virtualPCR (function in insect package with default arguments) with primers defined below.
Todo: check 2 warnings, doesn't affect assigntaxonomy().

##
Euka02 primers (Taberlet 2018)

PRIMER1='TTTGTCTGSTTAATTSCG'
PRIMER2='CACAGACCTGTTATTGC' 

Fasta: DADA2 format
https://www.dropbox.com/s/abs1k4dcd2qtcde/SILVA_132_trimmed_euka02_dada2_names.fasta?dl=0

Fasta: DADA2 format with marine macrophytes from Ortega et al. 2020 MEE
https://www.dropbox.com/s/iuh47zlh0e8c4ud/SILVA_132_trimmed_euka02_dada2_names_with_ortega_macroalgae.fasta?dl=0

rds: Insect trained dataset and fasta used to create tree
https://www.dropbox.com/s/ew6wmifgb90ybcs/SILVA_132_trimmed_euka02_insect_names.fasta?dl=0
https://www.dropbox.com/s/dw43l3qebtvwuuy/euka02_learn.rds?dl=0

##
  18s mini  V9    (Amaral-Zettler et al. 2009)
PRIMER1="CCCTGCCHTTTGTACACAC"
PRIMER2="CCTTCYGCAGGTTCACCTAC"

Fasta: DADA2 format
https://www.dropbox.com/s/b28w4s9xy54xj1v/SILVA_132_trimmed_18smini_dada2_names.fasta?dl=0

rds: Insect trained dataset and fasta used to create tree
https://www.dropbox.com/s/fybveejdufs6ktm/SILVA_132_trimmed_18smini_insect_names.fasta?dl=0
https://www.dropbox.com/s/0t5zv97xjvx7nh8/18smini_learn.rds?dl=0

####
   18s Universal  V4  (Stoeck et al 2010)
PRIMER1="CCAGCASCYGCGGTAATTCC"
PRIMER2="ACTTTCGTTCTTGATYRA"

Fasta: DADA2 format
https://www.dropbox.com/s/lhv526136tckugf/SILVA_132_trimmed_18s_stoeck_dada2_names.fasta?dl=0

rds: Insect trained dataset and fasta used to create tree
https://www.dropbox.com/s/x9ju5n0vua6jjzd/SILVA_132_trimmed_18s_stoeck_insect_names.fasta?dl=0
https://www.dropbox.com/s/47hd0czebm07qz1/18s_stoeck_learn.rds?dl=0

