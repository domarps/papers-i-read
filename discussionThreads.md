[Deep RL for Predicting and Tracking Popular Discussion Threads](http://arxiv.org/abs/1606.03667)
==================================================

####TL;DR : Non-personalized Media Recommendation and Trend Spotting in the social network of a target community. 

Since, the actual degree of hotness (reward) of a potential hot topic candidate is not immediately known, a Reinforcement Learning mechanism can estimate future reactions. A Deep RL architecture can handle the `combinatorial action` defined by natural language. The work is claimed to serve as a benchmark for tracking hot topics in social media with deep RL.

####Discussion:

* The approach is different from the Wolpertinger architecture to reduce computational complexity of evaluating all actions -- the actions defined by a natural language `vary over different states`.
* Since the `episode` is defined as a trail of text comments beginning from the original poster to the end, the agent picks the best action which affects both the next state and the future expected reward.
* The action is chosen from a given set of candidates which makes modeling Q value difficult.

####Architectures:

* Per-action DQN
* DRRN
* DRRN-Sum
* DRRN-BiLSTM






