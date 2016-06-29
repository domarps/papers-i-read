[End-to-end LSTM-based dialog control optimized with supervised and reinforcement learning](https://arxiv.org/abs/1606.01269#)
============================================================================================================

#####TL;DR:
The goal of the paper is to model task-oriented dialog systems. A Recurrent Neural Network (LSTM) maps raw dialog history to a distribution over system actions. A custom API declaring various business rules enables the LSTM to take actions in real world. The LSTM optimization process is performed via Supervised Learning and Reinforcement Learning.

####Key Points:

The problem of Dialog Systems is essentially solved by tackling two major sub-problems:
* **State Tracking** : Automatic inference of dialog history representation, because of state space issues
* **Action Selection** : Best of both worlds (SL + RL)
  * Supervised learning can provide “good” dialogs as for the neural network to memorize
  * Reinforcement learning enables LSTM to perform action selection

#### References
* [Denny Britz's notes](https://github.com/dennybritz/deeplearning-papernotes/blob/master/notes/e2e-dialog-control-sl-rl.md)


