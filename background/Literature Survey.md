### Differential Privacy
1. TensorFlow Privacy
  <br>[Introducing TensorFlow Privacy](https://blog.tensorflow.org/2019/03/introducing-tensorflow-privacy-learning.html)
1. Definitions, intuition and history :
<br>Blog
    1. [Why differential privacy is awesome](https://desfontain.es/privacy/differential-privacy-awesomeness.html)
    1. [Differential privacy in (a bit) more detail](https://desfontain.es/privacy/differential-privacy-in-more-detail.html)
    1. [Differential privacy in practice (easy version)](https://desfontain.es/privacy/differential-privacy-in-practice.html)
    1. [Almost differential privacy](https://desfontain.es/privacy/almost-differential-privacy.html)
    1. [Local vs. global differential privacy](https://desfontain.es/privacy/local-global-differential-privacy.html)
1. [Code for training the model](https://github.com/ebagdasa/differential-privacy-vs-fairness)
1. [MNIST trained in TensorFlow Privacy](https://github.com/tensorflow/privacy/blob/master/tutorials/Classification_Privacy.ipynb)
1. [ERAN for abstraction verification](https://github.com/eth-sri/eran)
    1. Save a TensorFlow model .tf file
    1. Edit the raw MNIST data file [here](https://github.com/eth-sri/eran/blob/master/data/mnist_test.csv) to include all images of a certain label
    1. Run ERAN, specifying perturbation epsilon to verify
