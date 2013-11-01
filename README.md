somatic-snv-test-data
=====================

This is example data for exploring SomaticSniper output. The data is from NA12878 (tumor) and NA12892 (normal) and represents a tiny chunk of chromsome 21. It was created from 1000 Genomes Project (http://www.1000genomes.org) data available in the following locations:
NA12892 - ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/data/NA12892/high_coverage_alignment/NA12892.mapped.ILLUMINA.bwa.CEU.high_coverage_pcr_free.20130906.bam
NA12878 - ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/data/NA12878/high_coverage_alignment/NA12878.mapped.ILLUMINA.bwa.CEU.high_coverage_pcr_free.20130906.bam
Build 37 reference - ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/technical/reference/human_g1k_v37.fasta.gz

Should you wish to recreate the files in this repository, they were processed as follows below.

bc. samtools view -hb NA12892.mapped.ILLUMINA.bwa.CEU.high_coverage_pcr_free.20130520.bam 21:10400000-10500000 > normal.bam
samtools view -hb NA12878.mapped.ILLUMINA.bwa.CEU.high_coverage_pcr_free.20130520.bam 21:10400000-10500000 > tumor.bam
samtools index normal.bam
samtools index tumor.bam
gunzip human_g1k_v37.fasta.gz
samtools faidx human_g1k_v37.fasta 21:1-10505000 > ref.fa
