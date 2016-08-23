### [Deterministic Policy Gradient Algorithms](http://jmlr.org/proceedings/papers/v32/silver14.pdf)
======================================================

###Policy Gradient Algorithms for End-to-end policy optimization

* They calcuate noisy estimates of the gradient of the `expected reward` of the policy and then update the policy in the gradient direction. 
* Traditionally, a stochastic policy gives a probability distribution over actions, after having observed a large pool of training examples

### Issues with vanilla-PG
* `Credit Assignment` : Difficulty in ascertaining the good actions from the others
*  Continuous Action Space

###Actor-Critic Algorithms

* The critic's output drives the learning of both the actor and the critic.
* Represent the policy function independent of the value function
* `Policy  = actor` and the `Value = critic`
* Actor produces an action given the current state of the environment
* Critic produces a Temporal Difference error signal given the state and resultant award. Note that the critic estimates the action value function `Q`, it would require the output of the actor as well.
* Deep RL can enable the representation of both actor and critic as Neural networks





