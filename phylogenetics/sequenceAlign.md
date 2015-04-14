#Multiple sequence alignment

##File formats: 
* `XXX.fas` is unaligned fasta format

* `XXX.afa` is aligned fasta format

* `XXX.phy` is aligned phylip format
  
##[mafft](http://mafft.cbrc.jp/alignment/software/) 
* program installed as `mafft` in path

* [web server](http://toolkit.tuebingen.mpg.de/mafft)

* general usage (will need to convert to phylip format to run a tree, or see parameter below)

`mafft XXX.fas > XXX.afa`

* align with G-INS-i (accurate method), sort sequences in output, output as phylip (the last parameter is useful for input into a tree building program, see MLphylogenetics.md)

`mafft --globalpair -maxiterate 16 --phylipout --reorder XXX.fas > XXX.phy`

* help

`mafft -h`

* [parameters for large trees](http://mafft.cbrc.jp/alignment/software/tips.html)

* [correcting for reverse complementation](http://mafft.cbrc.jp/alignment/software/adjustdirection.html)

##[muscle](http://www.drive5.com/muscle/index.htm)
* program installed as `muscle` in path

* [web server](http://www.ebi.ac.uk/Tools/msa/muscle/)

* general usage (will need to convert to phylip format to run a tree)

`muscle -in XXX.fas -out XXX.afa`

* help

`muscle -h`

##Alignment visualization

* [AliView](http://www.ormbunkar.se/aliview/) is a nice, lightweight program for both Windows and Mac that you can use to visualize your alignments.
