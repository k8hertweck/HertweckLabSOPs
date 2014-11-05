#Tree visualization in R

[Figtree](http://tree.bio.ed.ac.uk/software/figtree/) is also good for exporting publication-ready tree figures, but is limited in what manipulations you can perform.

The following commands aren't the most elegant R scripts, but they are written to be easily modifiable to suit different types of tree visualizations. Additional commands useful for tree manipulation and phylogenetic comparative methods in R can be found [here](http://www.r-phylo.org/wiki/Category:R_Help).

##File formats: 
* `XXX` is single tree in [newick](http://en.wikipedia.org/wiki/Newick_format) format

* `PATH/TO/FILE` is path to the directory with your tree and data files

* `names.txt` is text file with two (tab separated) columns, with quotation marks surrounding text strings: 1) full taxon names, 2) taxon names in tree file
  
##Installing all packages in the R [phylogenetics task view](http://cran.r-project.org/web/views/Phylogenetics.html)
This takes a little time, but may be useful if you plan on doing many phylogenetic analyses using R. Otherwise, install each package used below separately using `install.packages`.

```
install.packages("ctv")
library(ctv)
install.views("Phylogenetics")
```

##Setting path and loading necessary libraries
```
setwd("PATH/TO/FILE")
library(ape)
library(phytools)
```

##Importing tree
`mltree<-read.tree("XXX")`

##Rerooting tree
```
outgroup<-"OUTGROUP"
mltreerooted<-root(mltree, outgroup)
```

##Formatting tip labels: replacing short names from analysis with complete names for publication
```
names.dat<-read.delim2("names.txt",header=FALSE)
names<-data.frame(names.dat)
colnames(names)<-c("long","short")
mltree$tip.label<-names$long[match(mltree$tip.label,names$short)]
```

##Manipulating bootstrap support values


##Plotting tree with bootstrap support and scale bar; saving to PDF
```
pdf(file="tree.pdf")
plotTree(ladderize(mltree, right=FALSE), cex=0.3, label.offset=0.005)
nodelabels(mltree$node.label, cex=0.4, adj=c(1.2, -0.4), frame="n")
add.scale.bar(0,10, length=0.01, cex=0.4)
dev.off()
```

Modify any numerical values to adjust font size and placement. Also see options for exporting files in different formats (postscript can also be useful for publications).
