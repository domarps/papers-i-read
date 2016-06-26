## [Playing Atari with Deep Reinforcement Learning](https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf)


TL;DR : Deep learning techniques can approximate the value function of an RL algorithm much more accurately than standard method
because they find the adequate features for doing so. This insight led to a first breakthrough when a CNN was combined with a slightly modified version of the standard Q-Learning algorithm to get impressive results in a large set of challenging video game problem.


### Playing Atari games with raw-pixel images
##### Why Atari?
In sharp contrast to the needs of dataset in the evaluation pipeline in Supervised learning problems, Sequential Decision Making (a.k.a Reinforcement Learning) requires closed loop systems. Researchers designing simulators to test their algorithms is a blatant conflict of interest. Game Consoles such as ATARI 2600 is a very modest game and serves as an efficient test-bed.

![image](https://cloud.githubusercontent.com/assets/7057078/16360587/fa135474-3b1f-11e6-854b-a35878afbbd4.png)

#### Reinforcement Learning in n-grams

* Future **Discounted** return from time t onwards

