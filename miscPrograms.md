#Miscellaneous programs for phylogenetic analysis and inference

These programs and scripts are for quick and easy fixes to problems which occassionally arise.

##[SumTrees](https://pythonhosted.org/DendroPy/scripts/sumtrees.html)
Part of [DendroPy](https://pythonhosted.org/DendroPy/), which requires [python](https://www.python.org)

`BEST.tre` is the best-scoring ML or consensus tree

`BOOTSTRAPSET` is the collection of trees from a bootstrap analysis

`XXX.tre` is your output, or best scoring/consensus tree with bootstraps added

`sumtrees.py --decimals=0 --percentages --no-summary-metadata --output=XXX.tre --target=BEST.tre BOOTSTRAPSET`
