Focused Crawling using Temporal Difference-Learning
===================================================

The paper discusses how TD learning can be leveraged for link prediction in focused crawling and presents initial evaluations on a confined dataset. In their approach, every web page is represented as a finite-dimensional feature vector where each value corresponds to the existence or not of a specific keyword which is key to classify whether a page is relevant or not. The state of each page is determined by Temporal Difference Learning in order to minimize the state space. The relevance of a page depends on the set of keywords present in a page.

Neural Networks are used to estimate values of the different stages. During training session, the crawler randomly follows pages for a defined number of steps or until it reaches a relevant page. Each step represents the implementation of action *a* thus moving the agent from state *s*<sub>*t*</sub> to *s*<sub>*t*+1</sub>. The respective reward *r*<sub>*t*+1</sub> and the features of the state *s*<sub>*t*</sub> are used as input to the neural network which is tuned to evaluate the state’s potential of belonging to the right path.

During the crawling mode, the crawler maintains a priority list of links to be followed, the priorities are computed by the neural network. The state value of a child page is inherited by the value of its parent (the current page) or by the average value of its parents, in case the page is pointed by multiple pages.
