#Data and analysis organization

I recommend setting up a separate directory for each of your projects. This may be the location where you set up an R project. You can also organize the components of your project in a way that make sense for the particular research question.

Here is an example of one way you may choose to set up subdirectories:
* **data**: original, unmodified data files (directly downloaded .csv)
* **bin**: scripts
* **intermediate**: parsed data files
* **figures**: visualizations as .pdf

If you are working on a phylogenetics project, you may want to include more specific subdirectories:
* **data**: unaligned fasta (.fas)
* **bin**: scripts
* **alignments**: aligned fasta (.afa), phylip (.phy)
* **trees**: tree files (.tre)
* **figures**: visualizations as .pdf

