Deep Compression, DSD training and EIE: deep neural network model compression, regularization and hardware acceleration 
========================================================================================================================

#### TL;DR
Neural networks are both computationally intensive and memory intensive, making them difficult to deploy on mobile phones and embedded systems with limited hardware resources. To address this limitation, “Deep Compression” is developed to compress the deep neural networks by 10x-49x without loss of prediction accuracy. The authors claim that the "Dense-Sparse-Dense" training method regularizes CNN/RNN/LSTMs to improve the prediction accuracy of a wide range of neural networks given the same model size. The "Efficient Inference Engine" works directly on the deep-compressed DNN model and accelerates the inference, taking advantage of weight sparsity, activation sparsity and weight sharing, which is 13x faster and 3000x more energy efficient than a TitanX GPU.

#### Key Points



#### Notes/Questions
