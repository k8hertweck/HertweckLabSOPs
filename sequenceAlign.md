#Multiple sequence alignment

##File formats: 
>XXX.fas is unaligned fasta format

>XXX.afa is aligned fasta format

>XXX.phy is aligned phylip format
  
##[mafft](http://mafft.cbrc.jp/alignment/software/) 
>program installed as `mafft` in path

>[web server](http://toolkit.tuebingen.mpg.de/mafft)

>general usage

>`mafft XXX.fas > XXX.afa`

>align wiht G-INS-i (accurate method), sort sequences in output, output as phylip

>`mafft --globalpair -maxiterate 16 --phylipout --reorder XXX.fas > XXX.phy`

>[parameters for large trees](http://mafft.cbrc.jp/alignment/software/tips.html)

>[correcting for reverse complementation](http://mafft.cbrc.jp/alignment/software/adjustdirection.html)

##[muscle](http://www.drive5.com/muscle/index.htm)
>program installed as `muscle` in path

>[web server](http://www.ebi.ac.uk/Tools/msa/muscle/)

>general usage

>`muscle -in XXX.fas -out XXX.afa`

