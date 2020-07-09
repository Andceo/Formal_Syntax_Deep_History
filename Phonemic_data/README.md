# Formal Syntax and Deep History - RUHLEN
This folder contains the instructions, the xml files, the tree files, and the log files used in the BEAST analysis.
We tried different models that differ for:

- Clock Model (Strict Clock, Relaxed Clock (Exponential and Logarithmic), Random Clock)
- Tree Priors (Yule Model, Birth Death Model, Coalescent Constant Population, Coalescent Exponential Population, Coalescent Bayesian Skyline, Coalescent Extended Bayesian Skyline)

The Yule Model and the Birth Death model for the tree priors yielded the highest posterior probabilities (as long as a Strict Clock or Relaxed Clock is used). The best model has a Relaxed Clock Logarithmic model, which has a slightly higher posterior probabilities mean than the Relaxed Clock Exponential model and lower standard deviation. Cf. the PDF in FigS7.


1. **pnas1424033112.sd01.txt**: the Ruhlen dataset, from [Creanza et al. (2015)](https://www.pnas.org/content/112/5/1265).

2. **ruhlen.nex**: this file contains the Ruhlen dataset, limited to the languages overlapping with our dataset, in Nexus format.

3. **consensus_tree**: this file contains the consensus tree of the BEAST analysis and it has been formatted as to produce Figure 7. The best model that we determined is a Gamma Site Model with Substitution Rate = 1, a Mutation Death Model with death p = 0.1, a Exponential Model (Logarithmic) with clock rate = 1, and a uniform Yule model for the birth rate. The Monte Carlo Markov Chain produced 10,000,000 trees, 25% of which were used for the burn-in and discarded for the purpose of the calculation of the consensus tree. The tree is a consensus tree of 7,500 different trees sampled through the 7,500,000 trees (with a sample stored every 1000 generated trees) produced by the Monte Carlo procedure.
