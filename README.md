# Is Differential Privacy Fairly Robust?
## Authors
Chitrasen Mohanty, Scott Wang

## Problem and technique description

#### What is the problem you're trying to solve?
[Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf) show that a differentially private neural network exhibits "unfair accuracy", which is to say its accuracy decreases for minority groups. We tackle the question of whether differentially private neural networks have "unfair robustness": does a differentially private neural network's _robustness_ decline for minority groups?

#### What have people done about it and what are the limitations of existing techniques?
[Phan et al. 2019](https://arxiv.org/pdf/1903.09822.pdf) and [Pinot et al. 2019](https://arxiv.org/pdf/1906.07982.pdf) point out that privacy and robustness are correlated objectives, and [Tsipras, Santurkar, Engstrom et al. 2019](https://arxiv.org/pdf/1805.12152.pdf) demonstrate that there is an inherent tradeoff between robustness and accuracy.

As far as we can tell, the literature on adversarial robustness concentrates mostly on verifying the prediction output is constant within a fixed perturbation quantity. Instead, we wish to quantify robustness by the _maximum possible_ perturbation quantity for a constant prediction output.

[Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf), following literature on fairness, establishes the relationship between subgroup size and prediction output accuracy, parametrised on the differential privacy parameter. It is unknown whether there is a relationship between subgroup size and robustness, for varying differential privacy parameters.

#### What do you propose to do?
We follow the training methodology in [Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf) and will concentrate on the MNIST dataset. We will truncate a particular class within the dataset to varying degrees to create a minority class, train differentially private neural networks with varying differential privacy parameters (noise and clipping combined to influence epsilon), then perform abstraction-based verification using [ERAN](https://github.com/eth-sri/eran) on test sets of the majority and minority classes with varying perturbation quantities to determine robustness.

#### What are your measures of success?
Via this project, we shall demonstrate whether there exists a correlation between robustness and subgroup size, parametrised by the privacy parameter (epsilon). We are hoping to come up with a figure resembling Figure 2(b) in [Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf), with robustness on the ordinate axis. This will help us understand what tradeoff there might be between differential privacy and fair robustness.

---

## Week of 6 Apr

#### On a scale of 1-10, how do we rate our progress over the past week?
7

#### What did we accomplish from last week's tasks?
We got ERAN [compiling and running in Colab](https://github.com/CS839/is-differential-privacy-fairly-robust/commit/1ec777b041aaff4a9e79c0eb34f533dccb11c46e). ERAN's model input format does not appear to be documented at all, so we [reverse-engineered it](https://github.com/CS839/is-differential-privacy-fairly-robust/commit/6147daa693482fa02376edcbc97c9ff093217d13).

#### What problems or concerns do we have?
None.

#### What do we plan to accomplish do over the next week?
We will begin training models in Colab for parameter ranges of differential privacy optimisation noise and clipping, minority class truncation, and perturbation quantity.

---

## Week of 30 Mar

#### On a scale of 1-10, how do we rate our progress over the past week?
7

#### What did we accomplish from last week's tasks?
We switched to using a different abstraction verification library, [ERAN](https://github.com/eth-sri/eran), which can directly take TensorFlow models. We are working on compiling the dependencies within Colab.

#### What problems or concerns do we have?
We need to determine ranges for the differential privacy parameters (noise and clipping), degree of truncation of the minority class, and robustness (perturbation quantity) for our experiment.

#### What do we plan to accomplish do over the next week?
We will finish setting up ERAN so that it runs correctly within Colab.

---

## Week of 23 Mar

#### On a scale of 1-10, how do we rate our progress over the past week?
6

#### What did we accomplish from last week's tasks?
We studied [DiffAI](https://github.com/eth-sri/diffai). Its primary purpose appears to be to train robust neural networks, not to verify them.

#### What problems or concerns do we have?
DiffAI is a PyTorch-based library. We may have to figure out how to transmute our TensorFlow model into PyTorch.

#### What do we plan to accomplish do over the next week?
Our model is relatively simple (only a few convolutional and fully-connected layers). We will tackle Assignment 2 to get a sense of whether it might be easier to "manually" retrieve the model weights to undertake abstraction verification, as opposed to using DiffAI.

---

## Week of 9 Mar

#### On a scale of 1-10, how do we rate our progress over the past week?
8

#### What did we accomplish from last week's tasks?
We adapted [an MNIST model](https://github.com/tensorflow/privacy/blob/master/tutorials/Classification_Privacy.ipynb) from TensorFlow Privacy and replicated the result from the original paper using Google Colab.

#### What problems or concerns do we have?
We ran into [this TensorFlow Privacy issue](https://github.com/tensorflow/privacy/issues/40). It isn't very impactful since it only limits the number of training and test examples to be an integer multiple of the batch size.

#### What do we plan to accomplish do over the next week?
We will begin studying the use of DiffAI.

---

## Week of 2 Mar

#### On a scale of 1-10, how do we rate our progress over the past week?
10

#### What did we accomplish from last week's tasks?
We were able to run the original paper's code for MNIST, and have annotated the code with [comments](https://github.com/CS839/is-differential-privacy-fairly-robust/commit/87e7614e13c53d0fc96f6c0fb8ce7ea4003b6068).

#### What problems or concerns do we have?
The code as written is undesirably complex. We need to troubleshoot why the code reports the accuracy of the label with the truncated frequency as zero, which doesn't seem right.

#### What do we plan to accomplish do over the next week?
We will begin to refactor out the code so that the model can be extracted and verified.

---

## Week of 24 Feb

#### On a scale of 1-10, how do we rate our progress over the past week?
10

#### What did we accomplish from last week's tasks?
We have begun to read through the original code for [Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf).

#### What problems or concerns do we have?
The Diversity in Faces dataset does not appear to be available. We may need to change our dataset to MNIST (which trains faster anyway).

#### What do we plan to accomplish do over the next week?
We will attempt to replicate the results for MNIST in [Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf).

---

## Week of X

#### On a scale of 1-10, how do we rate our progress over the past week?

#### What did we accomplish from last week's tasks?

#### What problems or concerns do we have?

#### What do we plan to accomplish do over the next week?
