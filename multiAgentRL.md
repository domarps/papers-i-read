Deep Multiagent Reinforcement Learning for Partially Observable Parameterized Environments
========================================================================================================================

#### TL;DR
As software and hardware agents begin to perform tasks of genuine interest, they will be faced with environments too complex for humans to predetermine the correct actions to take. 
Three characteristics shared by many complex domains are:
* high-dimensional state and action spaces
* partial observability
* multiple learning agents 

To tackle such problems algorithms combine deep neural network function approximation with reinforcement learning. The paper first described using Recurrent Neural Networks(RNN) to handle partial observability in Atari games. Next, a multiagent soccer domain Half-Field-Offense is described and approaches for learning effective policies in this parameterized-continuous action space are enumerated.

#### What's next?
Hierarchial RL : possibility to observe different goal states.

#### Key terms:
- n-step Q-learning
- On-Policy Monte Carlo
- Taking on-policy approach in the beginning before switching to off-policy(Matthew's future work)

#### Key Slides from the seminar:

Presentation Outline

![outline](https://cloud.githubusercontent.com/assets/7057078/16018753/b178577e-315a-11e6-8e5e-9f1da9a48aea.PNG)

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

Note: observe the view cones. The exact positions and the velocities of the agents are not observable.

![thegame](https://cloud.githubusercontent.com/assets/7057078/16018640/345b61be-315a-11e6-86fa-4347ff95e1af.PNG)

![off-policy Monte Carlo](https://cloud.githubusercontent.com/assets/7057078/16018684/6160a1e2-315a-11e6-8de3-7ebdce2583ec.png)


![multiagentrl](https://cloud.githubusercontent.com/assets/7057078/16018837/17e4e07c-315b-11e6-84f7-3ff9316ccbdb.PNG)


More challenging as the action space is twice as large ~ learning to write : we have two hands but you use only 1 to write.

![centralized](https://cloud.githubusercontent.com/assets/7057078/16018853/29d611b6-315b-11e6-8256-330b6002f15b.PNG)

![parametersharing](https://cloud.githubusercontent.com/assets/7057078/16018914/6c2b206a-315b-11e6-9f85-29bd03de90e0.PNG)

#### Notes/Questions

