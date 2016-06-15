## [Continuous Control with Deep Reinforcement Learning](http://arxiv.org/pdf/1509.02971v5.pdf)

#### TL;DR
The authors have developed a network that can control simulated physical events via reinforcement learning. Their previous work with deep Q-networks learned to play Atari games via [Q-learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf). However, this cannot work for real systems because the action space is (essentially) infinite since 3D space is continuous. The model hopes to revive attempts to approximate the value function of RL algorithms into developmental robotics problems.


#### Key Points

- `Model-Free Reinforcement Learning`: system dynamics are not known
- `continuous action problems` require Q-learning to maximize a complex, non-linear function at each update
- `actor-critic architecture` assigns a separate parameter `actor` policy
- `Deep DPG(DDPG)`combined a previous approach, Deterministic Policy Gradient(DPG) with DQN
- The off-policy algorithm is preferred over policy gradient methods  which can succeed only on high-dimensional problems requiring a large sample space.
- DDPG learns policies using low-dimensional observations using an actor-critic architecture
- virtual robots which learn to perform the task themselves are controlled by the same network via the same set of parameters
- improved stability in the system 
- virtual robots are used since it takes 2.5 million steps of experience for training in a virtual environment

#### Deep Deterministic Policy Gradients

It is a `Model-free, Deep Actor Critic` architecture. It has two neural networks -- Actor learns a policy \pi and the critic evaluates the policy to estimate Q-values. Actor processes the state of the world and outputs the action as well as the next 6 possible values of the parameters associated with the state of the world. These outputs are fed to the critic which evaluates how well the actor has learnt the current state.

![ddpg](https://cloud.githubusercontent.com/assets/7057078/16067790/7c71c0ea-3274-11e6-94b4-27c806c302c2.PNG)


The critic is trained using the same temporal difference update as the *standard DQN* -- the Loss is the immediate reward and the gamma discounted Q-value of the next state.

However, the actor network is trained with gradients that are generated from the critic. 

Ask the critic : `How should I change the current action in order to get a higher Q-value estimate?`

Answer : `The critic gradient tells you that the 4 actions and the 6 parameters are to be changed leading to a higher Q-value.`



![training](https://cloud.githubusercontent.com/assets/7057078/16019257/e6207c2a-315c-11e6-9a96-3dce35e8a3ca.PNG)


#### Notes/Questions
> Interestingly, all of our experiments used substantially fewer steps of experience than was used by DQN learning to find solutions in the Atari domain. Nearly all of the problems we looked at were solved within 2.5 million steps of experience (and usually far fewer), a factor of 20 fewer steps than DQN requires for good Atari solutions. This suggests that, given more simulation time, DDPG may solve even more difficult problems than those considered here.

- Nearly 2.5 million steps needed for learning the basic rules of the system for practical applications
- If the original Deep Q-network problem is converted to a continuous one by mapping each button to the 0-1 interval, how will DDPG compare?
- Adapting this method to continuous tasks typically requires optimizing two function approximators on different objectives.
- This continuous action space `differs` from the natural language action space in that the action space is known. In the [DRRN approach](https://github.com/domarps/papers-i-read/blob/master/DRRN.md), the action space is inherently discrete although a continuous representation of it has been learnt.
- Another continuous variant of the Q-learning algorithm, Normalized Advantage Functions(NAF) is a considerably simpler alternative than DDPG.
