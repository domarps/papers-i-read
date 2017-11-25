## Progressive Growing of GANs for Improved Quality, Stability, and Variation


The main idea is that they train a GAN at a low resolution first, then iteratively add higher and higher upscaling units. They show extremely convincing results at 1024x1024.

#### WGAN technique

* the improved WGAN technique, but that this is orthogonal to their technique (as evidence, they also demonstrate good results without WGAN).
* by starting at low resolution and slowly ramping up, they are able to train faster (around 5x). This is pretty intuitive: it doesn't make sense to start adding details before the core structure of the content is sound.
* We also propose a simple way to increase the variation in generated images, and achieve a record inception score of 8.80 in unsupervised CIFAR10.
