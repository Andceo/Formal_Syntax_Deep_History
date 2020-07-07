# Formal Syntax and Deep History
Scripts and data from the paper "Formal Syntax and Deep History". This material is strictly confidential until the publication of the paper, after which the material will become publicly available. The repository contains the following files:

1. **table.txt**: this file contains the name of the languages and their 94 associated features (with values '1', '0', '?'), separated by a tab. 

2. **lang_info.csv**: this file contains information about the languages of the dataset

3. **dist.py**: this Python3 script takes the file ```table.txt``` as input and returns an output file called ```jaccard_distances.txt```, with Jaccard distances in matrix format. The syntax is simply ```python3 dist.py table.txt```. Note that features where either language shows a '?' are ignored for the purposes of the distance computation.

4. **jaccard_distances.txt**: this is the output of ```python3 dist.py table.txt```. By loading the file on the online software [Morpheus](https://software.broadinstitute.org/morpheus), a heatmap can be obtained. We recommend performing *Hierarchical Clustering*, specifying the options:

     - Metric -> Matrix values (from a precomputed distance matrix)
     - Linkage Method -> Average
     - Cluster -> Rows and Columns

     The clustering is used to make sure that the rows and columns are grouped according to their Jaccard distances, and not following the input order. From *Options*, we modified *Color Scheme* and uncheck the box *Relative Color Scheme*, which allowed us to force the maximum at 0.857 (which is the maximum Jaccard distance of the dataset), therefore obtaining a better resolution for the distance matrix. We also clicked on *Add Color Stop* at 0.43, and then selected the color Yellow, to obtain a better resolution of the table, so that it is easy to identify the distances on both sides of the middle.  
     
     The same file can be loaded on [PAST](https://folk.uio.no/ohammer/past/) to generate a Principle Coordinates Analysis (PCoA, which differs from the Principle Components Analysis, PCA, because it takes as input a distance matrix) by selecting:

     - Multivariate -> Ordination -> PCoA. 

     In the scatter plot, the attribute *Row Labels* must be selected to display the name of the languages.
     
5. **UPGMA**: this folder contains the material used for the UPGMA analysis.

6. **BEAST**: this folder contains the material used for the BEAST analysis.

7. **SplitsTree**: this folder contains the material used for the Network analysis.

8. **Phonemic data**: this folder contains the material used for the analysis of the Ruhlen database.

9. **Romance**: this folder contains the material used for the analysis of the Romance languages.







