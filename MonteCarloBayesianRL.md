[Monte Carlo Bayesian Reinforcement Learning](http://arxiv.org/abs/1206.6449)
=============================================================================
#### TL;DR
Partially Observable Markov Decision Process is an elegant and general model for planning under uncertainty. Applications for POMDPs include control of autonomous vehicles, dialog systems, and systems for providing assistance to the elderly. Learning problems such as reinforcement learning, making recommendations and active learning can also be posed as POMDPs. Unfortunately, solving POMDPs is computationally intractable. When the state space is not too large, conditions are defined under which solving POMDPs becomes computationally easier, and describe algorithms for solving such problems. The algorithms are extended to very large or infinite state spaces using Monte Carlo methods. 

##### POMDP Background
Partially Observable Markov Decision Process(POMDP) &lt;S, A, T, R , *Ω*, O&gt;
 - State S, Actions A and observations *Ω*
 - Transition Function T
 - Observation Probability O
 - Reward Function R 


##### Solving Discrete POMDPs
* Intractability
    - Finite horizon POMDP is **PSPACE-complete**(intractable in the worst case)
    - No polynomial-sized policy
* Easier to Approximate Subclasses
    - Many problems of practical interest are actually not so hard
* Reachable Beliefs
* Covering Number
* SARSOP

##### Bayesian Reinforcement Learning(BRL)

* Markov Decision Process(POMDP) &lt;S, A, T, R&gt; with unknown parameters *θ*
* Cast as POMDP with 
    - States *S*′=(*S* × *θ*)
    - Transition matrix dependent on *θ*
    - States fully observed
    - Prior belief b<sub>0</sub>(*θ*)
* Problem with employing approaches for solving discrete POMDPs
    - Parameters *θ* are often continuous. 
        - Think driver imperfection, reaction time, acceleration, deceleration parameters

##### Monte Carlo Bayesian Reinforcement Learning
* Online Phase
    - Sample K Hypotheses
    - Solve discrete POMDP
* Offline Phase
    - Execute Policy 
* Advantages
   - Not restricted to special prior distributions, unlike most BRL methods
   - Requires only that priors are easy to sample
   - Exploits effective discrete POMDP solvers
   - Handles both fully and partially observable domains

##### Conclusions
* POMDP elegant and general model for many interesting sequential decision problems
* For interesting applications, need to *scale* up to very large or continuous state spaces
