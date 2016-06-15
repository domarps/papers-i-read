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

##### Presentation Outline

![outline](https://cloud.githubusercontent.com/assets/7057078/16066490/92b1dd92-3268-11e6-9363-6ef823365a59.PNG)

##### Markov Decision Process

Simply observe the current state - learn the action to execute.

##### Partially Observable MDP

Instead of receiving the full state of the world, the agent only receives observations(which may be noisy and incomplete) -- the agent still performs actions a<sub>t</sub> and rewards r<sub>t</sub>.

![pomdp](https://cloud.githubusercontent.com/assets/7057078/16065909/9ca39a02-3263-11e6-9eb2-9023c5d0b2c5.PNG)

##### Introductory slide on RL

![RL](https://cloud.githubusercontent.com/assets/7057078/16065938/df2fef2e-3263-11e6-8b5a-52a014b7ff19.PNG)

##### Q-Value Function : Expected sum of $gamma$ discounted rewards from taking action a in state s. 

An optimal Q function yields an optimal policy -- it is important correctly estimate the every action from every state -- so that it is easy to learn to act optimally by simply choosing the action that maximizes the Q-function for each state.

![Q-value](https://cloud.githubusercontent.com/assets/7057078/16066220/4b774fe0-3266-11e6-869c-6dba45ae35bd.png)

##### Deep Neural Networks

![dnn](https://cloud.githubusercontent.com/assets/7057078/16066251/926bdbe6-3266-11e6-843b-085a7efe8456.PNG)

##### Recurrent Q-Learning for POMDPs -- The Atari Environment


##### Lillicrap's DDPG

![ddpg](https://cloud.githubusercontent.com/assets/7057078/16019295/220d85a2-315d-11e6-8093-8ad5e4b5bf55.PNG)

##### Training 

![training](https://cloud.githubusercontent.com/assets/7057078/16019257/e6207c2a-315c-11e6-9a96-3dce35e8a3ca.PNG)

##### Q-Learning Spectrum

![q-learning spectrum](https://cloud.githubusercontent.com/assets/7057078/16018336/f6e27904-3158-11e6-96fb-0a3a9ba92d0b.PNG)

##### Low Bias, High Variance Q-learning v/s High Bias, Low Variance Q-learning

![overview](https://cloud.githubusercontent.com/assets/7057078/16018374/181f40de-3159-11e6-8e15-e399fc17f1a0.PNG)

##### Monte-Carlo seminar

![monte-carlo](https://cloud.githubusercontent.com/assets/7057078/16018400/35a3a0dc-3159-11e6-9106-640b34b67b95.PNG)

##### Experiments

![experiments](https://cloud.githubusercontent.com/assets/7057078/16018522/a523e3ae-3159-11e6-8417-43907d495887.PNG)

##### Inverting Gradients -- can we use eligibility traces for update targets? 

Need to acquire the Monte-Carlo HV,LB approach as well stay computationally efficient.

![invertinggradients](https://cloud.githubusercontent.com/assets/7057078/16018553/cd0a5a24-3159-11e6-9b65-29415968a7d3.PNG)

Note: observe the view cones. The exact positions and the velocities of the agents are not observable.

![thegame](https://cloud.githubusercontent.com/assets/7057078/16018640/345b61be-315a-11e6-86fa-4347ff95e1af.PNG)

![off-policy Monte Carlo](https://cloud.githubusercontent.com/assets/7057078/16018684/6160a1e2-315a-11e6-8de3-7ebdce2583ec.png)

![multiagentrl](https://cloud.githubusercontent.com/assets/7057078/16018837/17e4e07c-315b-11e6-84f7-3ff9316ccbdb.PNG)

More challenging as the action space is twice as large ~ learning to write : we have two hands but you use only 1 to write.

![centralized](https://cloud.githubusercontent.com/assets/7057078/16018853/29d611b6-315b-11e6-8256-330b6002f15b.PNG)

![parametersharing](https://cloud.githubusercontent.com/assets/7057078/16018914/6c2b206a-315b-11e6-9f85-29bd03de90e0.PNG)

#### Related Work

![relatedwork](https://cloud.githubusercontent.com/assets/7057078/16019006/cd908980-315b-11e6-9e9a-d83caa251f11.PNG)


#### Future Directions
Reducing sample complexity but learn better policies, Non-differenitable components in RNN

![futuredirections-ii](https://cloud.githubusercontent.com/assets/7057078/16019070/077ae42e-315c-11e6-95b0-ffc952db5a0d.PNG)


#### Discussion(Notes/Questions):
- Instead of all joint space taking up exponential complexity
- Idea is to have a sequence of tasks to learn, curriculum to learn. promising direction for shaping rewards
- Implementation Question : mini-batch of size 32, number of steps 10 for backprop.
- Training time : LSTM receives a single frame with 10 time steps.
- RL is a little slower to learn policies, flexible to learn non-differentiabilties.
- Determistic Policy Gradient vs Stochastic Gradient
    * to address continuous action spaces
    * trade-off between TD methods to estimate Q-values v/s policy methods
- The critic must know [ToDo]
- Loss may not be able to tell you that you have converged.

