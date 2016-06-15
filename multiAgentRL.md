Deep Multiagent Reinforcement Learning for Partially Observable Parameterized Environments
========================================================================================================================

#### TL;DR
As software and hardware agents begin to perform tasks of genuine interest, they will be faced with environments too complex for humans to predetermine the correct actions to take. 
Three characteristics shared by many complex domains are:
* high-dimensional state and action spaces
* partial observability
* multiple learning agents 

To tackle such problems algorithms combine deep neural network function approximation with reinforcement learning. The paper first described using Recurrent Neural Networks(RNN) to handle partial observability in Atari games. Next, a multiagent soccer domain Half-Field-Offense is described and approaches for learning effective policies in this parameterized-continuous action space are enumerated.

#### What's next in store?
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

![mdp](https://cloud.githubusercontent.com/assets/7057078/16066896/084db212-326c-11e6-8920-5e07f693bc51.PNG)



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

Observation : Current game screen of the Atari Game(160x210 image with 3 channels)

![atari-i](https://cloud.githubusercontent.com/assets/7057078/16067020/49cfe8ee-326d-11e6-8136-91a7e1f694bc.PNG)
![atari-ii](https://cloud.githubusercontent.com/assets/7057078/16067021/4af42f1e-326d-11e6-9608-6697dd09aeca.PNG)

Are Atari Games MDPs or POMDPs? Depends on the number of game screens used in the state representation. 

Many games PO with a single frame - can tell the position of the ball but not the velocity!!

##### Deep Q-Network
Most successful approach to play Atari Games -- it estimates the Q-values for each of the 18 possible actions in an Atari Game. The DQN accepts the last 4 game screens as input. 
Learning via TD Reinforcement Learning  -- maintain a Replay Memory *D* -- sample transitions from the memory and make the target of the neural net *y* the *reward* plus the *gamma discounted Q-value of the next state encountered*.

![deepqn](https://cloud.githubusercontent.com/assets/7057078/16067022/4c2a59b2-326d-11e6-8fc8-8eda346e7d1b.PNG)

##### Flickering Atari

DeepMind have established that the DQNs perform very well on MDPs but the motivation is to test the performance in POMDPs.

![flickeringatari](https://cloud.githubusercontent.com/assets/7057078/16067023/4e1543cc-326d-11e6-9d48-6db972c1553d.PNG)

#### DQN Flickering Pong 
Here the Game state must be *inferred* with high probability from previous history of observations! DQN learns a flickering version of Pong not that well -- it seems to have establishing the position of the ball or inferring its velocity. Half of the 4 game screens are noisy -- the DQN however treats them as normal game screens. Reason : Not intended to handicap the algorithm.

##### Deep Recurrent Q-Network
Two major changes
    - Fully connected layer of DQN **replaced** with LSTM (Same number of nodes present in both layers)
    - Recurrence in the LSTM layer hopefully extracts the relevant information from the screen at the current timestep.
    
![deeprecurrentqn](https://cloud.githubusercontent.com/assets/7057078/16067025/4f490332-326d-11e6-9e0d-23d201e1232b.PNG)

BPTT : Back Propogation Through Time for the last ~~4~~ 10 timesteps.

The LSTM gives the DQN some redundancy in order to combat the noisy observations coming in. Hope is to infer what the current state of the world is, although the observations are noisy. It is important to note that the LSTM has *inferred* velocity of the Pong ball despite observing just a single frame at every timestep -- a sequence of inputs that **maximize the activation of a given LSTM unit**.


##### Performance Analysis

Note : Pong maxes out at 21

![performance](https://cloud.githubusercontent.com/assets/7057078/16067426/5f8a409a-3271-11e6-93b8-3c6699698ab5.PNG)

##### State Action Spaces

![sas](https://cloud.githubusercontent.com/assets/7057078/16066929/71596eb8-326c-11e6-84cb-3a6571a7759f.PNG)

Observe the view cones. The exact positions and the velocities of the agents are not observable.

##### Lillicrap's DDPG

![ddpg](https://cloud.githubusercontent.com/assets/7057078/16019295/220d85a2-315d-11e6-8093-8ad5e4b5bf55.PNG)

##### Training 

![training](https://cloud.githubusercontent.com/assets/7057078/16019257/e6207c2a-315c-11e6-9a96-3dce35e8a3ca.PNG)

##### Approaches to bound the DDPG action space

- Squashing Gradients   

        ![squashinggradients](https://cloud.githubusercontent.com/assets/7057078/16068066/73783818-3277-11e6-9b9a-20df93dfb798.PNG)

- Zero Gradients
        ![zeroinggradients](https://cloud.githubusercontent.com/assets/7057078/16068086/ad9a0616-3277-11e6-8c98-95c1d4ac57fe.PNG)

- Invert Gradients
        ![invertinggradients](https://cloud.githubusercontent.com/assets/7057078/16018553/cd0a5a24-3159-11e6-9b65-29415968a7d3.PNG)

##### Q-Learning Spectrum

![q-learning spectrum](https://cloud.githubusercontent.com/assets/7057078/16018336/f6e27904-3158-11e6-96fb-0a3a9ba92d0b.PNG)

##### Low Bias, High Variance Q-learning v/s High Bias, Low Variance Q-learning

![overview](https://cloud.githubusercontent.com/assets/7057078/16018374/181f40de-3159-11e6-8e15-e399fc17f1a0.PNG)

##### Monte-Carlo 

![monte-carlo](https://cloud.githubusercontent.com/assets/7057078/16018400/35a3a0dc-3159-11e6-9106-640b34b67b95.PNG)

##### Experiments

![experiments](https://cloud.githubusercontent.com/assets/7057078/16018522/a523e3ae-3159-11e6-8417-43907d495887.PNG)

##### Inverting Gradients -- can we use eligibility traces for update targets? 

Need to acquire the Monte-Carlo HV,LB approach as well stay computationally efficient.

![invertinggradients](https://cloud.githubusercontent.com/assets/7057078/16018553/cd0a5a24-3159-11e6-9b65-29415968a7d3.PNG)

##### Snapshot of the Game

![thegame](https://cloud.githubusercontent.com/assets/7057078/16018640/345b61be-315a-11e6-86fa-4347ff95e1af.PNG)

##### Off-Policy Monte Carlo

![off-policy Monte Carlo](https://cloud.githubusercontent.com/assets/7057078/16018684/6160a1e2-315a-11e6-8de3-7ebdce2583ec.png)

##### Deep Multiagent RL

![multiagentrl](https://cloud.githubusercontent.com/assets/7057078/16018837/17e4e07c-315b-11e6-84f7-3ff9316ccbdb.PNG)

More challenging as the action space is twice as large ~ learning to write : we have two hands but you use only 1 to write.

![centralized](https://cloud.githubusercontent.com/assets/7057078/16018853/29d611b6-315b-11e6-8256-330b6002f15b.PNG)

![parametersharing](https://cloud.githubusercontent.com/assets/7057078/16018914/6c2b206a-315b-11e6-9f85-29bd03de90e0.PNG)

##### Related Work

![relatedwork](https://cloud.githubusercontent.com/assets/7057078/16019006/cd908980-315b-11e6-9e9a-d83caa251f11.PNG)


##### Future Directions
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

