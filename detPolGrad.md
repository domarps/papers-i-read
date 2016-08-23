### [Deterministic Policy Gradient Algorithms](http://jmlr.org/proceedings/papers/v32/silver14.pdf)
======================================================

###Policy Gradient Algorithms for End-to-end policy optimization

* They calcuate noisy estimates of the gradient of the `expected reward` of the policy and then update the policy in the gradient direction. 
* Traditionally, a stochastic policy gives a probability distribution over actions, after having observed a large pool of training examples
