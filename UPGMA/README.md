# Formal Syntax and Deep History - UPGMA
This folder contains the instructions and the files to generate the UPGMA tree in the paper.

1. **table_labels.txt**: calculating the UPGMA tree first requires modifying the ```table.txt``` file using the labels instead of the full names of the languages, since the software that we use to calculate the UPGMA tree does not allow long names. We therefore create a file called ```table_labels.txt```. 

2. **jackknife.py**: before running UPGMA, we have implemented a Python3 script that allows us to sample the input matrix, in order to obtain a distribution of trees and estimate a consensus tree. Since the Jaccard distance between two pairs excludes all parameters that are set to '0' in either language, a standard bootstrapping procedure runs the risk of making a pair of two languages not comparable, because the number of identities plus differences can be zero, and then yield a zero denominator for the Jaccard formula. For this reason, we decided to adopt a quasi-jackknife procedure, by creating 1000 datasets in which six parameters are removed, and are replaced by six parameters of the dataset. Since the minimum number of comparable parameters between any two languages in the dataset is seven, a resampling of six parameters will assure that the two strings are comparable by means of the Jaccard distance. The syntax of the script is ```python3 jackknife.py number_of_samples input_file output_file```. After the resampling procedure, the script calculates distance matrices. We run ```python3 jackknife.py 1000 table_labels.txt jackknife-output.txt```.

3. **jackknife-output.txt**: the output of the ```jackknife.py``` script, containing 1000 distance matrices. 

4. **upgma-trees**: the ```jackknife-output.txt``` can be processed by the packages included in the classic [PHYLIP](http://evolution.genetics.washington.edu/phylip.html) software (Felsenstein 1994). Please [download PHYLIP](http://evolution.genetics.washington.edu/phylip/getme-new1.html) on your computer. We use ```neighbor``` to read the input file, specifying two options. For *Neighbor-joining or UPGMA tree*, we specify *UPGMA*. From *Analyze Multiple data sets*, we specify *1000*. We are then asked to provide a random seed, and the software will start calculating UPGMA trees for our distance matrices. The output file is called ```outtree``` by defaut, but we renamed it ```upgma-trees``` to avoid future clashes (since this is the default name of all PHYLIP programs).

5. **consensus_tree**: we use ```consensus``` to generate the final Newick file containing the consensus tree. We specify *Yes* for *Trees to be treated as Rooted* to root the tree. The output file of consensus is named ```outtree``` by defaut, but we renamed it ```consensus-tree```.

6. **consensus_tree.nex**: The output file can be easily read using [Mesquite](http://www.mesquiteproject.org) (Maddison and Maddison 2018). Just make sure that the Newick file is in a single line. The settings of the tree in Figure 3 are saved in ```consensus-tree.nex```. Note that [FigTree](http://tree.bio.ed.ac.uk/software/figtree/) reads the consensus scores from PHYLIP files as branch lengths, and therefore opening this file with FigTree will not reproduce the same figure.





