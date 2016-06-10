# FastQC in Galaxy

FIXME: include screenshots

FIXME: include file location and/or choose different input.

## Introduction

After sequencing, the reads should be checked for their quality. This tutorial demonstrates how to use the tool called FastQC to examine bacterial paired-end sequence reads from Illumina. The FastQC website is [here.](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/)

## Learning Objectives

At the end of this tutorial you should be able to:

1. run FastQC on input sequence reads, and
2. examine the FastQC output.

## Input files

e.g. <fn>mutant_R1.fastq</fn> and <fn>mutant_R2.fastq</fn>: a paired-end read set  
FIXME: or alternative. Ideally with contaminants/etc. ?

We will evaluate the R1 input reads using the FastQC tool.

## Run FastQC

- Go to <ss>Tools &rarr; NGS:Analysis &rarr; NGS: QC and Manipulation &rarr; FastQC</ss>
- for <ss>Short read data from your current history</ss>: <fn>mutant_R1.fastq</fn>
- Click <ss>Execute</ss>

## Examine output files
Once finished, examine the output called <fn>FastQC on data1:webpage</fn> (Hint: click the eye icon). It has a summary at the top of the page and a number of graphs.

Look at:

-   <ss>Basic Statistics: Sequence length</ss>: will be important in setting maximum k-mer size value for assembly
-   <ss>Basic Statistics: Encoding</ss>: Quality encoding type: important for quality trimming software
-   <ss>Basic Statistics: % GC</ss>: high GC organisms don’t tend to assemble well and may have an uneven read coverage distribution.
-   <ss>Basic Statistics: Total sequences</ss>: Total number of reads: gives you an idea of coverage.
-   <ss>Per base sequence quality</ss>: Dips in quality near the beginning, middle or end of the reads: determines possible trimming/cleanup methods and parameters and may indicate technical problems with the sequencing process/machine run.
-   <ss>Per base N content</ss>: Presence of large numbers of Ns in reads: may point to poor quality sequencing run. You would need to trim these reads to remove Ns.
-   <ss>Kmer content</ss>: Presence of highly recurring k-mers: may point to contamination of reads with barcodes, adapter sequences etc.

We have warnings for two outputs (per base sequence content; Kmer content). This would warrant more investigation.

General questions you might ask about your input reads include:

- How good is my read set?
- Do I need to ask for a new sequencing run?  
- Is it suitable for the analysis I need to do?

For a fuller discussion of FastQC outputs and warnings, see the [FastQC website link](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/), including the section on each of the output [reports](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/Help/3%20Analysis%20Modules/), and examples of ["good"](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/good_sequence_short_fastqc.html) and ["bad"](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/bad_sequence_fastqc.html) Illumina data.



## What Next?
- Trim reads with [Trimmomatic.](trimmomatic.md)

FIXME: include these?

- link to a fastqc protocol:
http://vlsci.github.io/lscc_docs/tutorials/assembly/assembly-protocol/#section-1-read-quality-control

- more detailed information:
https://docs.google.com/document/pub?id=16GwPmwYW7o_r-ZUgCu8-oSBBY1gC97TfTTinGDk98Ws