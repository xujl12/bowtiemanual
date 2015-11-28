# bowtiemanual
The simple guideline leads mapping the sequencing reads from the start point of download database



1.dowdload database from ensembl website.

  switch to the Dowdload website and then go to the database website. Choose the species you need. Dowdload the .gtp file from the geneset directory and the .fasta file of the genome.
  
2.extract the transcriptome .fasta file by using .gtp and genome.fasta and gttread command.

  gffread -w transcript.fa -g genome.fa .gtf
  
3.build the bowtie2 index by bowtie2-build.

  bowtie2-build transcript.fa transcript
  
4.map the reads by bowtie2 and get the sam file.

  bowtie2 -x index -U reads/ -1 read1 -2 read2 -s output.sam
