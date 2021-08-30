# Musing

## Introduction

This directory records the contents of musings.  

Muse is a set of script which help build Mu2e repos. A musing is a Muse build area that has been published on cvmfs for general use.  Please see the [wiki](https://mu2ewiki.fnal.gov/wiki/Muse) for further details on Muse and musings.

Each musing has a name, for example, SimJob, which indicates what is in the musing build.  In the case of SimJob, it contains builds of Offline and Production repos.  Each musing may have several versions.

Each musing depends on other repos. The dependence may be through the content of the repo itself or through a link to content already published on cvmfs.  For example the musing "Offline" contains the build of a tag of Offline.  The musing called "Production" contains the build of the tag of the Production repo, but the musing "SimJob" contains only links to specific version these other two builds.

The expectaion is that musings may be built using scripts and the configuration from this directory.

## Configuration rules

* for each musing there is a file with the same name as the musing
* for each version of the musing, the file will contain one line indicating the dependencies
* the first word of the line will be the version of the musing
* the remaining words on the line each represent a dependence
* if the repo will be built as part of the musing,  the word should be of the form "repoName/version", for example, "Offline/v10_00_00"
* if the dependence should be linked, the word should be of the form "link/repoName/version", for example, "link/Production/v01_01_01"
* if an envset should be specified in the build, it is an additional word, of the form "envset/number", for example "envset/p011"
* multiple lines are allowed for one version, but they should differ only by the envset, for example Offline version X might be built with the tagged envset and published.  Later it might be needed to publish an additional build with the same tag, but a specific new envset, with, for example, a test verison of geant.
* lines starting with # are ignored as comments
* blank lines are ignored


