# Formal Syntax and Deep History - SplitsTree
This folder contains the instructions files used in the NeighborNet analysis, through [SplitsTree](https://software-ab.informatik.uni-tuebingen.de/download/splitstree4/welcome.html) (Huson and Bryant 2006).

1. **table_splitstree.nex**: this file contains the dataset in Nexus format. The only difference with the file used in the BEAST analysis is that this file contains labels rather than the full names of the languages, for visualization purposes. By opening this file with SplitsTree, you will automatically get a NeighborNet analysis, which will reproduce the network displayed in Figure 5.

2. **scores.txt**: delta scores and q-residuals from the NeighborNet analysis. In order to obtain them, do:
    * Analysis -> Compute Delta Scores
    
3. **delta.py**: this Python3 script creates a scatter plot of the delta scores derived from the NeighborNet analysis. It requires that you have the package ```matplotlib``` installed. Its syntax is ```python3 delta.py scores.txt```.

4. **qresid.py**: this Python3 script creates a scatter plot of the q-residuals derived from the NeighborNet analysis. It requires that you have the package ```matplotlib``` installed. Its syntax is ```python3 qresid.py scores.txt```.

5. **Fig5.pdf**: this is the SplitsTree network reported in the article (Figure 5).



