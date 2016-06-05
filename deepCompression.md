Deep Compression, DSD training and EIE: deep neural network model compression, regularization and hardware acceleration 
========================================================================================================================

#### TL;DR
Neural networks are both computationally intensive and memory intensive, making them difficult to deploy on mobile phones and embedded systems with limited hardware resources. To address this limitation, this talk first introduces “Deep Compression” that can compress the deep neural networks by 10x-49x without loss of prediction accuracy[1][2][5]. Then this talk will describe DSD, the "Dense-Sparse-Dense" training method that regularizes CNN/RNN/LSTMs to improve the prediction accuracy of a wide range of neural networks given the same model size[3]. Finally this talk will discuss EIE, the "Efficient Inference Engine" that works directly on the deep-compressed DNN model and accelerates the inference, taking advantage of weight sparsity, activation sparsity and weight sharing, which is 13x faster and 3000x more energy efficient than a TitanX GPU[4].

#### Key Points



#### Notes/Questions
