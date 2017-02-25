---
layout: post
title: "seqMeta 1.6.5 Released"
author: "Brian Davis"
date: "25 February, 2017"
published: true
status: publish
draft: false
output: html_document
---
 
[![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/seqMeta)](http://cran.r-project.org/web/packages/seqMeta)
 
## Release Summary
 
This release fixes a couple edge cases which were handled incorrectly.  The minimum `coxme` package version was bumped to 2.2-4 as it changed the definition of variance component estimates in `lmekin`. Minor changes to user documentation and examples were also made.
 
 
## seqMeta 1.6.5
 
* `prepScores` and `prepScores2` scaled theta incorrectly when using a kinship matrix.
* `prepCox` function calculates the projection matrix incorrectly for collinear variants in the same gene.
* Minimum `coxme` version moved to 2.2-4. 
* Explicitly passed formula to `check_format_skat`.  Previously relied on calling environment to define formula.
* Return p-value of `NA` if standard error is 0 in burdenMeta and singlesnpMeta.
* Fixed `impute_to_mean` from producing an error in odd circumstances.
* Added verbose functionality to `prepScores2`.
* Added examples to `prepScores2` documentation.
* Explicitly import all functions in packages other than base to comply with new CRAN policy. 
 
See NEWS for a complete list of changes.
