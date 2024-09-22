# Learning the topology of a Bayesian Network from a database of cases using the K2 algorithm
## Acknowledgements
This is the final project for the 'Advanced Statistics for Physics Analysis' course in the 'Physics of Data' master program, University of Padua.
Group: <a href=https://github.com/emanuele-quaglio>Emanuele Quaglio</a>, <a href=https://github.com/FilippoCucchetto>Filippo Cucchetto</a>, Giulia Bellentani. 
## The problem
When working with a database of records, one useful approach is to build a probabilistic network that can reveal the dependencies between the variables in the data. This network can then be applied to predict the future behavior of the system being studied [2]. Despite notable advancements in both the theory and practical implementation of belief networks, the actual process of constructing these networks tends to be challenging and time-consuming. An efficient method is required to estimate the relative likelihoods of various belief-network structures, given a collection of cases and a set of specific assumptions.
## The algorithm
The K2 algorithm [3] is a greedy search method used to construct Bayesian networks by incrementally adding parent nodes to each variable, maximizing the posterior probability of the network structure. It operates under the assumption of a predefined node ordering and uses the following scoring function to evaluate potential parent sets for each node:
<p align=center>$f(i, \pi_i)=\prod_{j=1}^{q_i}\frac{(r_i-1)!}{(N_{ij}+r_i-1)!}\prod_{k=1}^{r_i}\alpha_{ijk}!$</p>

## Network reconstruction
The space of possible node orderings is explored both in a uniformly random way, and through a version of Metropolis-Hastings Monte Carlo Markov Chain algorithm, taking inspiration from [4].
![image](https://github.com/user-attachments/assets/d373edf7-a78d-4a5c-b027-770d59bf35e6)

### References
[1] M. Scutari and J.B. Denis, Bayesian Networks, CRC Press (2022), Taylor and Francis Group

[2] G.F. Cooper and E. Herskovitz, A Bayesian Method for the Induction of Probabilistic Networks from Data,
Machine Learning 9 (1992) 309

[3] C. Ruiz, Illustration of the K2 Algorithm for learning Bayes Net Structures,
http://web.cs.wpi.edu/~cs539/s11/Projects/k2_algorithm.pdf

[4] Kuipers, J., Suter, P., & Moffa, G. (2022). Efficient Sampling and Structure Learning of Bayesian Networks. Journal of Computational and Graphical Statistics, 31(3), 639–650. https://doi.org/10.1080/10618600.2021.2020127
