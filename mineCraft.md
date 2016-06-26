[Control of Memory, Active Perception, and Action in Minecraft](https://arxiv.org/abs/1605.09128)
================================================================

#####TL; DR:
The authors introduce and evaluate 3 neural network architectures to extend DQN with a form of memory. Two notable contributions :
* A new Deep RL benchmark on maze-based Minecraft games is proposed with a difficulty intermediate between Atari Games and Continuous Tasks that thoroughly exercise memory needs.
* Network architectures for incorporating memory into deep RL and an empirical evaluation to convincingly demonstrate an improvement in generalization from adding memory.
The paper is another step towards addressing an open question in Deep RL : how can memory be used to deal with partial observability?

#####Discussion:
The task is a combination of combined delayed rewards with partial observability and a high-dimensional visual input. Care is taken to observe the generalization of architectures via task variations and division of task instances into test and train buckets.

#####Notes/Questions to ask:
* The proposed memory-based RL architecture should also be evaluated on standard benchmarks such as Atari.
* It is also important to understnd external memory size influence on performance.
* The part describing the memory, read-function and the controller were a bit harder to follow without specific background.

#####References:

* [Video Demo](https://www.youtube.com/watch?v=jQg8p-V8jF4)
* [Paper Review](http://icml.cc/2016/reviews/1242.txt)
