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
We follow the training methodology in [Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf) and will concentrate on the Flickr face dataset, which contains images of human faces with unevenly distributed skin tones. We will train differentially private neural networks with a varying privacy parameter (epsilon), then repeatedly perform abstraction-based verification using DiffAI with varying perturbation quantities on test sets of majority and minority group face images to determine robustness.

#### What are your measures of success?
Via this project, we shall demonstrate whether there exists a correlation between robustness and subgroup size, parametrised by the privacy parameter (epsilon). We are hoping to come up with a figure resembling Figure 2(b) in [Bagdasaryan, Shmatikov 2019](http://www.cs.cornell.edu/~shmat/shmat_neurips19.pdf), with robustness on the ordinate axis. This will help us understand what tradeoff there might be between differential privacy and fair robustness.

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
