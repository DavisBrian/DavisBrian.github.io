---
layout: post
title: "seqMeta Genotypes - Part II"
author: "Brian Davis"
date: "25 February, 2017"
published: true
status: publish
draft: false
output: html_document
---
 
#### *"I'm running your pipeline on our new data set but it's taking much longer than our previous data set.  Could you take a look at it?"* - local post doc
 
 
At the same time in the [CHARGE consortium](http://depts.washington.edu/chargeco/wiki/Main_Page) we are making cloud based "apps" on [DNAnexus](https://www.dnanexus.com/usecases-charge) to allow analyst throughout the consortium to conduct analysis in a uniform manner and with consistent reporting of results.  The current "app" is based on a **very** old version of the same pipeline referred to by the post doc.
 
 
This series of posts came from that simple enough sounding request, the similar issues we are encountering in the CHARGE consortium, and the rabbit hole I fell into that is optimization.
 
See [Part I](http://davisbrian.github.io/seqMeta_speedup_1/) for more background.
 
 

 
## Memory Requirements
 
## How does the format affect object size in memory?
 
![plot of chunk unnamed-chunk-1](/figures/unnamed-chunk-1-1.png)
 
## Minimum System Memory Requirements
 

|Data Set |  Format  | Object Size (GB) | Imputed Size (GB) |
|:--------|:--------:|:----------------:|:-----------------:|
|ExChip   |   gds    |       0.00       |        NA         |
|ExChip   | genotype |       0.36       |       0.72        |
|ExChip   |  sparse  |       0.10       |       0.07        |
|Freeze4  |   gds    |       0.00       |        NA         |
|Freeze4  | genotype |       3.91       |       7.81        |
|Freeze4  |  sparse  |       0.25       |       0.20        |
|Freeze5  |   gds    |       0.00       |        NA         |
|Freeze5  | genotype |       6.06       |       12.11       |
|Freeze5  |  sparse  |       0.32       |       0.26        |
 
## Imputation can decrease sparse matrix object size.
 
![plot of chunk unnamed-chunk-3](/figures/unnamed-chunk-3-1.png)
 
 
## Computation Time
 
 
## Genome-Wide MAF
![plot of chunk unnamed-chunk-4](/figures/unnamed-chunk-4-1.png)
 
 
## Gene-by-Gene MAF
![plot of chunk unnamed-chunk-5](/figures/unnamed-chunk-5-1.png)
 
## pseudo prepScores calculation (seqMeta)
![plot of chunk unnamed-chunk-6](/figures/unnamed-chunk-6-1.png)
 
## pseudo prepScores calculation continued...

|Data Set |  Format  | Total Time (hrs) | # Chroms |
|:--------|:--------:|:----------------:|:--------:|
|ExChip   |   gds    |       0.4        |    24    |
|ExChip   | genotype |       0.0        |    24    |
|ExChip   |  sparse  |       0.3        |    24    |
|Freeze4  |   gds    |       7.6        |    24    |
|Freeze4  | genotype |       1.7        |    24    |
|Freeze4  |  sparse  |       0.9        |    24    |
|Freeze5  |   gds    |       39.1       |    24    |
|Freeze5  | genotype |       5.8        |    24    |
|Freeze5  |  sparse  |       12.0       |    24    |
 
## Thoughts
 
 
In the next post I'll look at...
