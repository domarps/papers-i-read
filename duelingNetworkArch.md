[Dueling Network Architectures for Deep Reinforcement Learning](http://arxiv.org/abs/1511.06581)
=============================================================
#####TL; DR:
An alternative architecture + learning scheme for Deep Q-Networks(DQN) is proposed in the paper. The Q-function approximation is achieved by decomposing the Q function into a state value and the advantage value. Concretely, the action values Q(s,a) can be written as the sum of a state-dependent offset V(s) and the advantage A(s,a) for specifically taking action a in that state, such that:
                              Q(s,a) = V(s) + A(s,a)

The action value is represented with a network architecture that features *two* channels, representing the state value and the advantages. The channels are merged to obtain an estimated action value. The following image (stolen from [Link](https://hadovanhasselt.wordpress.com/2016/06/20/best-paper-at-icml-dueling-network-architectures-for-deep-reinforcement-learning/)) captures the distinction between a conventional DQN and the duel network 

![image](https://cloud.githubusercontent.com/assets/7057078/16360009/66f75d0e-3aff-11e6-915c-9ace33a342ab.png)

As we follow the convolutional layers, we observe that the convolutional network is forked the network into two streams of fully connected feed-forward computation.

######Notes/Questions:
* This paper highlights that until now the standard neural networks (CNNs, MLPs and LSTMs) have been used to perform this Q function approximation have been standard neural networks. The authors suggest that the task of Q function approximation can benefit from an architecture *specially* designed for reinforcement learning.
* This approach, albeit a minor modification to the architecture and training of DQNs improves the state-of-the-art as observed in the Atari Learning Environment benchmark.
* The work is a huge motivator for the optimal representation of Q value approximators. It has been demonstrated many times that even **slightly better** approximations to the Q function yield significant improvements in reinforcement learners, so reinforcement-learning specific architectures to improve the Q function approximation seems a natural approach to take. 

######References:
* [Reviews](http://icml.cc/2016/reviews/927.txt)
* [Author's Blogpost](https://hadovanhasselt.wordpress.com/2016/06/20/best-paper-at-icml-dueling-network-architectures-for-deep-reinforcement-learning/)





