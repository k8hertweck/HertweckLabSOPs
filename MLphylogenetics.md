#ML phylogenetic tree inference

##File formats:
>XXX.afa is aligned fasta format

>XXX.phy is aligned phylip format

>XXX is job name (used in output files)

>OUTGROUP is the taxon used as an outgroup (optional)

>RANDOM# is a randomly selected number

##Model selection
>Maximum likelihood (ML) phylogenetic inference uses a model of evolution to searchand assess possible tree topologies. Use a program like [jModelTest](https://code.google.com/p/jmodeltest2/) to select the best-fitting model of molecular evolution for a particular dataset.

##[raxml](http://sco.h-its.org/exelixis/web/software/raxml/index.html)
>program installed as `raxml` in path

>[web server](http://embnet.vital-it.ch/raxml-bb/)

>RAxML is designed for large datasets, and has a limited number of model parameters.

>search for best-scoring ML tree and run 1000 rapid bootstrap replicates under GTR+G

>`raxml -f a -# 1000 -n XXX -o OUTGROUP -m GTRGAMMA -x RANDOM# -s XXX.phy -p RANDOM#`

##[phyml](http://www.atgc-montpellier.fr/phyml/binaries.php)
>program installed as `phyml` in path

>[web server](http://atgc.lirmm.fr/phyml/)

>PhyML also has a menu-based command line interface which you can access by entering `phyml`

>search for best-scoring ML tree and run 1000 bootstrap replicates under GTR+G and otherwise default parameters

>`phyml -i XXX.phy -d nt -n 1 -b 1000 -run_id XXX -m GTR -f m -c 4 -a e -o tlr -s NNI`

