#Maximum likelihood (ML) phylogenetic tree inference

##File formats:
* `XXX.afa` is aligned fasta format (if your alignment is in this format, you can convert it to phylip using a [web server](http://genome.nci.nih.gov/tools/reformat.html); output as PHYLIP-Seq) 

* `XXX.phy` is aligned phylip format 

* `XXX` is job name (used in output files)

* `OUTGROUP` is the taxon used as an outgroup (optional)

* `RANDOM#` is a randomly selected number

##Model selection
Maximum likelihood (ML) phylogenetic inference uses a model of evolution to search and assess possible tree topologies. Use a program like [jModelTest](https://code.google.com/p/jmodeltest2/) to select the best-fitting model of molecular evolution for a particular dataset. You may need to change parameters in the scripts below if a the selected model differs from GTR+G. Note: I choose not to use the parameter I (proportion of invariant sites).

##[raxml](http://sco.h-its.org/exelixis/web/software/raxml/index.html)
* program installed as `raxml` in path

* [web server](http://embnet.vital-it.ch/raxml-bb/)

* RAxML is designed for large datasets, and has a limited number of model parameters.

* search for best-scoring ML tree and run 1000 rapid bootstrap replicates under GTR+G

`raxml -f a -# 1000 -n XXX -o OUTGROUP -m GTRGAMMA -x RANDOM# -s XXX.phy -p RANDOM#`

* Several files are output from this analysis. The most important are:
	* `RAxML_info.XXX` (specifies the parameters used to run the analysis, also describes the input data)
	* `RAxML_bipartitions.XXX` (the highest scoring likelihood tree with bootstrap support values annotated on branches, newick format)

##[phyml](http://www.atgc-montpellier.fr/phyml/binaries.php)
>program installed as `phyml` in path

>[web server](http://atgc.lirmm.fr/phyml/)

>PhyML also has a menu-based command line interface which you can access by entering `phyml`

>search for best-scoring ML tree and run 1000 bootstrap replicates under GTR+G from sequential phylip alignment (default tree searching options in effect). Change to -b 0 to skip bootstrap analysis.

>`phyml -i XXX.phy -d nt -q -n 1 -b 1000 -run_id XXX -m GTR -f m -c 4 -a e -o tlr -s NNI`

>Several files are output from this analysis. The most important are:
>>XXX.phy_phyml_stats_XXX.txt (specifies the parameters used to run the analysis, also describes the input data)
>>XXX.phy_phyml_tree_XXX.txt (the highest scoring likelihood tree with bootstrap support values annotated on branches, newick format)