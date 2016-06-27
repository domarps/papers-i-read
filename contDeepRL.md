[Continuous Deep Q-Learning with Model-based Acceleration](http://arxiv.org/abs/1603.00748)
===========================================================================================

####TL;DR:
The paper aims to bring generality of model-free Deep Reinforcement Learning into real-world domains by reducing sample complexity. The paper has two key contributions:
*  `Normalized Advantage Function (NAF)` approach for parameterization of the Q-value function enables efficient training of the Q-learning procedure with experience replay.
* `Imagination Rollouts` is a new type of model-guided exploration, where a dynamics model is used to generate both -ve and +ve trajectories added to the experience relay buffer.

The authors describe an approach for applying Q-Learning to problems with continuous states and actions, while using neural networks as function approximators. The Q-function is represented in terms of the value function and the advantage function, while the value function parameterized quadratically w.r.t the action.

The feasibility of the Q-learning task is achieved by estimating the mean/co-variance of the NAF using a deep network -- thus making it possible to evaluate the max of the Q-function using a simple forward pass through the value and advantage function networks.


#####Notes/Questions to ask:

* The approach requiring the estimation of parameters, V(s), mu(s), and P(s) is an interesting alternative to estimation of parameters in actor-critic type methods, Q(s,a) and pi(s).
* The authors' claim for improved performance hinges on two facts : Quadratic function acts as a regularizer and that the learning signal for all the estimators come directly from the environment.


#####References:
* [Paper Reviews](http://icml.cc/2016/reviews/1274.txt)
* [Deep-RL-TensorFlow](https://github.com/carpedm20/deep-rl-tensorflow)



