Deep Compression, DSD training and EIE: deep neural network model compression, regularization and hardware acceleration 
========================================================================================================================

#### TL;DR
Neural networks are both computationally intensive and memory intensive, making them difficult to deploy on mobile phones and embedded systems with limited hardware resources. To address this limitation, “Deep Compression” is developed to compress the deep neural networks by 10x-49x without loss of prediction accuracy. The authors claim that the "Dense-Sparse-Dense" training method regularizes CNN/RNN/LSTMs to improve the prediction accuracy of a wide range of neural networks given the same model size. The "Efficient Inference Engine" works directly on the deep-compressed DNN model and accelerates the inference, taking advantage of weight sparsity, activation sparsity and weight sharing, which is 13x faster and 3000x more energy efficient than a TitanX GPU.

#### Slides I understood(or hope to understand :v: : 
![bitsperweight](https://cloud.githubusercontent.com/assets/7057078/15988105/4eae4fb6-2ff9-11e6-8692-bd856fd91e24.PNG)
![deepcompression-i](https://cloud.githubusercontent.com/assets/7057078/15988108/4eaed4f4-2ff9-11e6-8e49-63d52fed8366.PNG)
![deepcompression-pipeline](https://cloud.githubusercontent.com/assets/7057078/15988107/4eaee0f2-2ff9-11e6-8d05-690dbc56415d.PNG)
![densesparsedensetraining](https://cloud.githubusercontent.com/assets/7057078/15988109/4eb2294c-2ff9-11e6-96ba-315f1f54deff.PNG)
![finetunecentroids](https://cloud.githubusercontent.com/assets/7057078/15988106/4eae700e-2ff9-11e6-99e7-7e3281107589.PNG)
![modelcompression](https://cloud.githubusercontent.com/assets/7057078/15988110/4eb4de12-2ff9-11e6-9c7b-e1a4be610efb.PNG)
![networkpruning](https://cloud.githubusercontent.com/assets/7057078/15988114/4ec0547c-2ff9-11e6-8f7b-0397e0b5ff4a.PNG)
![neuralmachinetranslation](https://cloud.githubusercontent.com/assets/7057078/15988111/4ebc5a66-2ff9-11e6-8716-f16d5bba6d34.PNG)
![pruning_neuraltalk_lstm](https://cloud.githubusercontent.com/assets/7057078/15988113/4ebdc630-2ff9-11e6-9e6d-b5fed8086bd6.PNG)
![pruning trainedquantization](https://cloud.githubusercontent.com/assets/7057078/15988112/4ebd8b5c-2ff9-11e6-848d-6fb2a45d1c50.PNG)
![pruning-i](https://cloud.githubusercontent.com/assets/7057078/15988115/4ec0f260-2ff9-11e6-8eb1-31e7bd152844.PNG)
![pruningneuralmachinetranslation](https://cloud.githubusercontent.com/assets/7057078/15988116/4ec4f5c2-2ff9-11e6-818b-f374a40763ad.PNG)
![pruning-result](https://cloud.githubusercontent.com/assets/7057078/15988117/4ecaa3a0-2ff9-11e6-966f-fe88bec6fb97.PNG)
![pruning-rnn-lstm](https://cloud.githubusercontent.com/assets/7057078/15988119/4ecc9390-2ff9-11e6-8b91-a2ec2ab47b42.PNG)
![retraintorecover](https://cloud.githubusercontent.com/assets/7057078/15988118/4ecb9f26-2ff9-11e6-9713-ecdb5ae710f8.PNG)
![smallerdnn](https://cloud.githubusercontent.com/assets/7057078/15988120/4ece74ee-2ff9-11e6-9550-62a2d2565fe4.PNG)
![speedefficiency](https://cloud.githubusercontent.com/assets/7057078/15988121/4ecffb0c-2ff9-11e6-84f6-a03ff904c551.PNG)
![sram-dnn](https://cloud.githubusercontent.com/assets/7057078/15988122/4ed404e0-2ff9-11e6-864a-f7709c6237ed.PNG)
![weightdistribution](https://cloud.githubusercontent.com/assets/7057078/15988123/4ed91c0a-2ff9-11e6-8a5f-cecb97ee16c0.PNG)
![weightsharing](https://cloud.githubusercontent.com/assets/7057078/15988124/4ed9d00a-2ff9-11e6-85b9-ff32fadcc689.PNG)
![weightsharing-ii](https://cloud.githubusercontent.com/assets/7057078/15988125/4edc1bf8-2ff9-11e6-8fb3-fe811cc20d3d.PNG)
![weightsharing-iii](https://cloud.githubusercontent.com/assets/7057078/15988126/4edfabba-2ff9-11e6-9b6a-93257966acae.PNG)


#### Notes/Questions
