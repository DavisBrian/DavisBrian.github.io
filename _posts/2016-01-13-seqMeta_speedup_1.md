---
layout: post
title: "Big Data and seqMeta - Part I (Genotypes)"
author: "Brian Davis"
date: "14 January, 2016"
published: true
status: publish
draft: false
output: html_document
---
 
#### *"I'm running your pipeline on our new data set but it's taking much longer than our previous data set.  Could you take a look at it?"* - local post doc
 
 
At the same time in the [CHARGE consortium](http://depts.washington.edu/chargeco/wiki/Main_Page) we are developing cloud based "apps" on [DNAnexus](https://www.dnanexus.com/usecases-charge) to allow analyst throughout the consortium to conduct analysis in a uniform manner and with consistent reporting of results.  The current "app" is based on a **very** old version of the same pipeline referred to by the post doc.
 
 
This series of posts came from that simple enough sounding request for help, the similar issues we are encountering in the CHARGE consortium, and the rabbit hole I fell into that is optimization.
 
 
## Background
 
For those less familiar with genomic data analysis in epidemiological studies there are three key data structures needed to run a typical [seqMeta](https://cran.r-project.org/web/packages/seqMeta/index.html) analysis.  
 
* *genotype* matrix - Subjects X SNPs dosage matrix of [0, 1, 2, NA], representing the number of alleles which differ from the reference genotype.
 
* *SNPInfo* - data frame that maps SNPs to groups of SNPS to be analyzed together (like genes).  
 
* *phenotype* - data frame with a response variable and covariates, similar to data used by `lm`.
 
With these 3 data structures seqMeta aims to be an efficient way to analyze problems of the type `phenotype ~ covariates + SNP(s)` over a large number of SNPS and/or groupings of SNPS.
 
 
## Genotype Data
 
While I can't share our actual data I'll share some summary statistics of 3 typical data sets.
 
* [ExomeChip](http://www.chargeconsortium.com/main/exomechip) - a typical smaller data set.
* [Freeze4]   - the *previous* data set referred to by the post doc
* [Freeze5]   - the *new* data set referred to by the post doc 
 

 

|Data Set| SNPs  |Subjects|Pct 0's|Pct 1's|Pct 2's|Pct NA's|
|:-------|:-----:|:------:|:-----:|:-----:|:-----:|:------:|
|ExChip  |246672 |  3856  | 89.92 | 4.49  | 1.80  |  3.78  |
|Freeze4 |1797859|  5718  | 97.75 | 0.67  | 0.44  |  1.14  |
|Freeze5 |2041614|  7810  | 98.07 | 0.55  | 0.36  |  1.03  |
 
## The Problem
These data sets have grown from being able to run all chromosomes combined together on a standard office PC to several gigabytes of genomic data for each chromosome.  With this growth in data so has the memory requirements and computational time needed to run a standard analysis.
 

|Data Set | Total Size (GB) | Largest Chromosome (GB) |
|:--------|:---------------:|:-----------------------:|
|ExChip   |      7.11       |          0.72           |
|Freeze4  |      76.71      |          7.81           |
|Freeze5  |     118.93      |          12.11          |
 
An analysis with the Exome Chip data takes roughly a coffee refill. Freeze4 analysis takes 3-4 hours. The post doc reported Freeze5 was "taking well over 24 hrs before I killed the job".  Over 24 hours clearly isn't realistic, the number of analyses typically run at a time would measure weeks.  
 
 
## Potential Solutions
 
While there are many different ways to deal with this ever growing data size.  I'll look at three commonly proposed solutions.
 
* Keep the traditional genotype matrices and either split them up in units smaller than a chromosome, increase the memory on computer systems used to run these analyzes, and/or distribute the work load over several machines in parallel.
 
* Store the traditional genotype matrix on disk in either in a database or in a binary file, reading in and analyzing a portion at a time. The CHARGE Consortium is looking at Genomic Data Structure (**GDS**) Format implemented in the [SeqArray](http://bioconductor.org/packages/release/bioc/html/SeqArray.html) package.
 
* Store the genotypes in a sparse matrix format as implemented in the [Matrix](https://cran.r-project.org/web/packages/Matrix/index.html) package.
 
## Traditional Genotype Matrix
 
* Stored on disk as integer matrix in compressed RData format.
* In-memory size = 4 bytes per genotype + overhead.
* Imputing to mean changes the data type to numeric and in-memory size doubles.
* Standard matrix operations apply.
 
## GDS Genotype Matrix
 
* Same as the traditional genotype matrix but stored on disk in Genomic Data Structure (GDS) Format.
* File size highly dependent on input VCF.
* Imputing to mean cannot be directly stored in GDS format.
* In-memory size = traditional genotype matrix of the same data.
 
## Sparse Genotype Matrix
 
* Stored on disk as numeric sparse matrix in compressed RData format.
* In-memory size = 8 bytes per non-zero genotype + overhead. 
* Imputing to mean does not change data type and in-memory size stays the same or is reduced.
* Most standard matrix operations apply
 
 
 
In the next post I'll look at how each of these formats affect memory requirements and computation times.
 
