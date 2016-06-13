Deep Multiagent Reinforcement Learning for Partially Observable Parameterized Environments
========================================================================================================================

#### TL;DR
As software and hardware agents begin to perform tasks of genuine interest, they will be faced with environments too complex for humans to predetermine the correct actions to take. 
Three characteristics shared by many complex domains are:
* high-dimensional state and action spaces
* partial observability
* multiple learning agents 

To tackle such problems algorithms combine deep neural network function approximation with reinforcement learning. The paper first described using Recurrent Neural Networks(RNN) to handle partial observability in Atari games. Next, a multiagent soccer domain Half-Field-Offense is described and approaches for learning effective policies in this parameterized-continuous action space are enumerated.


Key terms:
- n-step Q-learning
- On-Policy Monte Carlo
- Taking on-policy approach in the beginning before switching to off-policy(Matthew's future work)

#### Key Slides from the seminar:

Q-Learning Spectrum

![q-learning spectrum](https://cloud.githubusercontent.com/assets/7057078/16018336/f6e27904-3158-11e6-96fb-0a3a9ba92d0b.PNG)

Low Bias, High Variance Q-learning v/s High Bias, Low Variance Q-learning

![overview](https://cloud.githubusercontent.com/assets/7057078/16018374/181f40de-3159-11e6-8e15-e399fc17f1a0.PNG)

Monte-Carlo seminar

![monte-carlo](https://cloud.githubusercontent.com/assets/7057078/16018400/35a3a0dc-3159-11e6-9106-640b34b67b95.PNG)

Experiments
![experiments](https://cloud.githubusercontent.com/assets/7057078/16018522/a523e3ae-3159-11e6-8417-43907d495887.PNG)

Inverting Gradients -- can we use eligibility traces for update targets? Need to acquire the Monte-Carlo HV,LB approach as well stay computationally efficient.

![invertinggradients](https://cloud.githubusercontent.com/assets/7057078/16018553/cd0a5a24-3159-11e6-9b65-29415968a7d3.PNG)




#### Notes/Questions

