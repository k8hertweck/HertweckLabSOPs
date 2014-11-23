#Extract or reorder sequences in a fasta file

##File formats:
* `XXX.fas` is a fasta file

* `XXX.fas.cidx` index file created by `cdbfasta`

* `list.txt` is the names of sequences you want to extract

* `XXXout.fas` is the fasta file including only sequences named in `list.txt`

##[Fasta file indexing and retrieval](http://cdbfasta.sourceforge.net)
This set of programs is quite stable and works well for large data files. There are two steps: (1) index the original fasta file, (2) extract sequences from index file.

```
cdbfasta XXX.fas 
cat list.txt | cdbyank XXX.fas.cidx -o XXXout.fas
```

##in python
https://www.biostars.org/p/1709/

##in perl
https://www.biostars.org/p/1195/
