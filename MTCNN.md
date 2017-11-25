## Face alignment using MTCNN

The Dlib face detector misses some of the hard examples (partial occlusion, silhouettes, etc). This makes the training set too "easy" which actually deteriorates model performance on certain benchmarks. To solve this, other face landmark detectors has been tested. One face landmark detector that has proven to work very well in this setting is the Multi-task CNN.
