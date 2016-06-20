[Dueling Network Architectures for Deep Reinforcement Learning](https://hadovanhasselt.wordpress.com/2016/06/20/best-paper-at-icml-dueling-network-architectures-for-deep-reinforcement-learning/)
=============================================================

#####TL; DR
The elegant main idea of the paper is to separate the value of a state and the advantage value for each action in that state.  Concretely, the action values Q(s,a) can be written as the sum of a state-dependent offset V(s) and the advantage A(s,a) for specifically taking action a in that state, such that:
