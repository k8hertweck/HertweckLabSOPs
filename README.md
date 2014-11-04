PhylogeneticSOPs
================

Standard operating procedures for generic phylogenetics methods.

These files are short cheat sheets for my preferred methods to run in a bash shell or in R; they assume a basic understanding of the command line (see [my website](https://sites.google.com/site/k8hertweck/resources/bioinformatics-skills) for a genearl overview and an explanation of installing and running these programs). Each file is not meant to be run on a given file; instead, extract the script for your particular method of interest and paste into the command line or another script, replacing XXX (described at the beginning of each document) with your filenames. 

Scripts assume nucleotide data, unless amino acid (protein) data is otherwise specified. If you are starting with unaligned nucleotide data, you will likely consult the files in the following order:

* `sequenceAlign.md` multiple sequence alignment

* `MLphylogenetics.md` Maximum likelihood tree inference

* `treeViz.md` tree visualization

Additional (but less often used) scripts can be found in `miscPrograms.md`
