# Musing

## Introduction

This directory records the contents of musings.  

Muse is a set of script which help build Mu2e repos. A musing is a Muse 
build area that has been published on cvmfs for general use.  
Please see the [wiki](https://mu2ewiki.fnal.gov/wiki/Muse) 
for further details on Muse and musings.

Each musing has a name, for example, SimJob, which indicates what is 
in the musing build.  In the case of SimJob, it contains a build
of the Production repo and backing link to an Offline. 
Each musing may have several versions.

The expectaion is that musings may be built using scripts and the 
configuration from this directory.

## Configuration file rules

* lines starting with # are ignored as comments
* blank lines are ignored
* for each published musing there is a file with the same name as the musing
* for each version of the musing, the file will contain one line 
   indicating the dependencies
* the first word of the line will be the version of the musing
* the remaining words on the line each represent a dependence
* if the repo will be built as part of the musing,  the word should be of 
   the form "repoName/version", for example, "Offline/v10_00_00"
* if the dependence should be a backing link, the word should be of 
   the form "backing/repoName/version", for example, 
   "backing/Offline/v01_01_01"
* if an envset should be specified in the build, it is an additional word, 
  of the form "envset/number", for example "envset/p011"
* if one version of a repo is built against different envsets, it would
  look like:
v10_15_00    Offline/v10_15_00
v10_15_00a   Offline/v10_15_00 envset/p010
* if dependencies change through backing links, those would be similar
MDC2020r  Production/v00_09_02   backing/Offline/v10_15_01
MDC2020s  Production/v00_09_02   backing/Offline/v10_15_02


