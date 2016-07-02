[Trust Region Policy Optimization](https://arxiv.org/abs/1502.05477)
============================================

####TL;DR:
The success of	neural	networks	in	supervised	learning	relies	on	the	fact	that	learning	reduces	to	a	nonlinear	optimization	problem. An improved understanding of monotonic behavior can fully wield the power of non-linear function approximators in RL (which has been rather slow to adopt such NLFA). The authors aim to *achieve monotonic policy improvement*, both in theory and practice. A good policy should be applicable to arbitrary policy parameterization as well as should be able to provide guidance about step-size selection.

###Contributions:

A policy update scheme with monotonic improvement guarantee has inspired a practical trust region algorithm to demonstrate the robustness on challenging domains.

####Problem Setup:
Consider a Markov Decision Process (MDP)
![image](https://cloud.githubusercontent.com/assets/7057078/16541782/00df1dd4-4042-11e6-8236-3c0659ab8f41.png)




