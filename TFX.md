## TFX: A TensorFlow-Based Production-Scale Machine Learning Platform


The main idea is to describe a homegrown machine learning platform. 

## AI ?

The AI model is after all just a tiny part of what goes into using machine learning in production systems. TFX has been claimed to have empowered Google Play engineers to standardize these moving parts, simplify the platform configuration, and reduce production time from **O(weeks)** to **O(days)**, while providing platform stability that minimizes disruptions. Here is the platform:

![image](https://user-images.githubusercontent.com/7057078/33226670-1eeb4b5c-d148-11e7-83f4-69fd0a8b3266.png)

## Data?

- Early identification and elimination of data anomalies downstream propogation saves a lot of wasted time later on.


## Multi-model training, evaluation

 - *Warm Start* : When training a new version of NN, the parameters corresponding to warm-start features are initialised from a previously trained version of the model, and fine tuning begins from there.
 - Supports only Tensorflow models. 


## Tensorflow Serving

- Production-scale Deployment 
- How does this stack against Flask or AWS Lambda?

The paper is an easy read, with no math! Highly recommend checking it out

References:

-- [Blog](https://blog.acolyer.org/2017/10/03/tfx-a-tensorflow-based-production-scale-machine-learning-platform/)
-- [KDD 2017](http://www.kdd.org/kdd2017/papers/view/tfx-a-tensorflow-based-production-scale-machine-learning-platform)
