# Training_datasets
Training datasets for dada2 and insect pipelines, see rep for available primers
Attributes of the fasta are formatted following the DADA2 protocal with 
the following taxonomy which will need to be input in DADA2 assigntaxonomy function
c("superkingdom","kingdom","phylum","class","order","family","genus","species")


####################################################
rbcl mini (Little)
The rbcl data base was created by searching the ncbi web site (see R code) on 19 May 2018 using the 
rentrez and insect packages with the following terms "(rbcl[All Fields] AND (Embryophyta[Organism] OR Plants[All Fields]) 
AND 00000000001[SLEN] : 00000010000[SLEN]) NOT (Metazoa[Organism] OR animals[All Fields]))".  
Sequence size was limited to <10,000 bp. 

All sequences from search
https://www.dropbox.com/s/g4ldcm5q0wen0qv/rbcl_embry_plants_1_10k__cut.fasta?dl=0
only sequences that passed cutadapt
https://www.dropbox.com/s/m22u8mbj79rioc1/rbcl_embry_plants_1_10k_dada2_rbclmini_cut.fasta?dl=0



####################################################
Euka02 primer (Taberlet 2018)
cut primer (cutadapt) from Silva database (SILVA_132_SSURef_Nr99_tax_silva_trunc).
Todo: check 2 warnings, doen't affect assigntaxonomy.

https://www.dropbox.com/s/ilh6l5ryln8u63a/silva_euka02_bothprim_dada_names.fasta?dl=0
