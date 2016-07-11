[Generative Adversarial Networks](https://arxiv.org/abs/1406.2661)
=============================================================================
#### TL;DR
The paper extends generative adversarial networks (GANs) to learn a generator network and a discriminator network to learn to generate images from a sentence as well map an image to the sentence. The approach requires solving two sub-problems:
  * Learn a text feature representation that captures the important visual details
  * Use these features to synthesize a compelling image that a human may mistake for real
  
#### The Scourge of Multi-modality
Deep learning has made great strides in solving the problem, however the one issue which is not solved is that hat the distribution of images conditioned on a text description is highly multimodal, in the sense that there are very many plausible configurations of pixels that correctly illustrate the description. 

#### Generative Adversarial Networks [[Karpathy's visualization](http://cs.stanford.edu/people/karpathy/gan/)] [[Soumith's eyescream](http://soumith.ch/eyescream/)]
* Optimize the Generator Network (G) to *fool* the he adversarially-trained discriminator (D) into predicting
that synthetic images are real.
* Both are competing in a two-player minimax game -- the discriminator tried to distinguish real training data from synthetic images while the generator tries to fool the discriminator.

#### char-CNN-RNN

#### Contributions
The contribution lies in the architecture, as well as two components:
* A matching-aware discriminator (CLS) 
* A manifold interpretation technique (INT)


##### Discussions/Questions
* The main limitation of this model and other similar ones is that, so far, they are only able to generate images from the very narrow distribution they were trained on (birds or flowers here).
