## [Continuous Control with Deep Reinforcement Learning](http://arxiv.org/pdf/1509.02971v5.pdf)

TLDR; The authors have developed a network that can control simulated physical events via reinforcement learning. Their previous work with deep Q-networks learned to play Atari games via Q-learning. However, this cannot work for real systems because the action space is (essentially) infinite since 3D space is continuous.


#### Key Points


- combined a previous approach, Deterministic Policy Gradient(DPG) for learning continuous action spaces with DQN to form Deep DPG(DDPG)
- DDPG learns policies using low-dimensional observations.
- virtual robots which learn to perform the task themselves are controlled by the same network via the same set of parameters
- improved stability in the system 
- virtual robots are used since it takes 2.5 million steps of experience for training in a virtual environment


#### Notes/Questions
> Interestingly, all of our experiments used substantially fewer steps of experience than was used by DQN learning to find solutions in the Atari domain. Nearly all of the problems we looked at were solved within 2.5 million steps of experience (and usually far fewer), a factor of 20 fewer steps than DQN requires for good Atari solutions. This suggests that, given more simulation time, DDPG may solve even more difficult problems than those considered here.

- Nearly 2.5 million steps needed for learning the basic rules of the system for practical applications
- If the original Deep Q-network problem is converted to a continuous one by mapping each button to the 0-1 interval, how will DDPG compare?