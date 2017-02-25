---
layout: post
title: "seqMeta 1.6.0"
author: "Brian Davis"
date: "25 February, 2017"
published: true
status: publish
draft: false
output: html_document
---
 
seqMeta 1.6.0 Released 
 
[![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/seqMeta)](http://cran.r-project.org/web/packages/seqMeta)
 
## Release Summary
 
This release fixes a couple edge cases which were handled incorrectly.  The minimum R version was bumped to 3.1.0.  One new function `prepScores2` was added.
 
 
## seqMeta 1.6.0
 
* Migrated to git / github
    + Bug Reports and Feature Requests should be submitted [github](https://github.com/DavisBrian/seqMeta/issues).
* Minimum R version moved to 3.1.0
* Duplicated SNP in snpinfo gene no longer pulls from the genotype matrix twice.
* Monomorphic snps with caf != 0 were handled incorrectly.
* Binomial models when genotypes imputed outside of seqMeta did not match when models were imputed by seqMeta.  Very slight differences in the covariance structure.
* Replaced `any(is.na(Z))` with `anyNA(Z)`
* Genotype range test now checks that they are [0, 2].
* SNPInfo in seqMetaExamples had incorrect type of snpNames and aggregateBy.
* Automatically convert (with warning) aggregateBy and snpName columns to type character if they are not already.
* Added new function prepScores2
 
 
### prepScores2
 
prepScores2 is a drop in replacement for prepScores, prepScoresX and prepCox. The only difference is the family argument should be text. `gaussian()` becomes `"gaussian"`, `binomial()` becomes `"binomial"` and `"cox"` is used for survival models. 
