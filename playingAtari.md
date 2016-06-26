## [Playing Atari with Deep Reinforcement Learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)


#####TL;DR:
Deep learning techniques can approximate the value function of an RL algorithm much more accurately than standard method
because they find the adequate features for doing so. This insight led to a first breakthrough when a CNN was combined with a slightly modified version of the standard Q-Learning algorithm to get impressive results in a large set of challenging video game problem.


### Playing Atari games with raw-pixel images
##### Why Atari?
In sharp contrast to the needs of dataset in the evaluation pipeline in Supervised learning problems, Sequential Decision Making (a.k.a Reinforcement Learning) requires closed loop systems. Researchers designing simulators to test their algorithms is a blatant conflict of interest. Game Consoles such as ATARI 2600 is a very modest game and serves as an efficient test-bed.

![image](https://cloud.githubusercontent.com/assets/7057078/16360587/fa135474-3b1f-11e6-854b-a35878afbbd4.png)

#### Reinforcement Learning in n-grams

* Future **Discounted** return starting from a given state at time t conditioned on the actions taken in the trajectory.
![image](https://cloud.githubusercontent.com/assets/7057078/16360614/1bdadc84-3b21-11e6-836e-f9bba3232534.png)
* Policy maps states to actions
* Q-Value of executing action *a* in state *s* followed by *\pi*
![image](https://cloud.githubusercontent.com/assets/7057078/16360615/290284c0-3b21-11e6-8096-62c3f3652f33.png)

* The Optimal Q-value function Q* which maximizes over different policies -- on expanding it, we get the Bellman equations (involving both the zero-step prediction and the one-step prediction using the same Q-value) as shown below:

![image](https://cloud.githubusercontent.com/assets/7057078/16360630/b01cdaf0-3b21-11e6-8f39-06a2162e8d56.png)

* Q* defines an optimal policy 

#### Approximating Q* in Practice

The issue is complicated in practice since the transition model is unknown and the feature space is a large high-dimensional one.

#### Deep Q Networks (Mnih et al. 2013)

**Train a convolutional network to predict/optimize Q-values (model-free)**
* Learn *online* from interaction data **off-policy (Q-learning like)**
* Minimally processed input -- no hand coded feature extraction
* Sample architecture and hyperparameters for different games
* State-of-the-art results

#### Deep Q Network Architecture

![dqn](https://cloud.githubusercontent.com/assets/7057078/16360672/13b5ab36-3b23-11e6-8b15-ce8ea5883856.jpg)

The input is the last 4 frames of the image and the filters are computed independently : essentially these are 8 X 8 X 4.
Note : the two layers of convolutions with Rectified Linear activation, using the same filter across the image to extract lower level features of the images.

Notice that the target y is independent of the theta parameter.
![image](https://cloud.githubusercontent.com/assets/7057078/16360685/b0f1434c-3b23-11e6-8e06-f0ccf10a761a.png)



