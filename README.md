# Perceptron Learning Algorithm 

### This is programmed in R programming language

## Synopsis of The Perceptron  
   The Perceptron learning algorithm is an algorithm that is used for supervised learning of binary clusters.The supervised learning involves giving conditions(inputs) with documented outputs. An allusion of learning and the binary clusters means that the choice of output has only two outcomes. The Perceptron was invented in 1957 by Frank Rosenblatt Ph.D. The idea is that the Perceptron works just like the neuron of a nervous system. Each neuron receives thousands of signals from other neurons, connected via synapses. Once the sum of the signals being received surpasses a certain threshold, a response is sent through the axon.

![Neuron Perceptron picture](neuronperceptron.png)

## Composition of the Perceptron Learning Algorithm
The implementation of the perceptron learning algorithm involves using a collection of features to answer a question that has two choices; binary cluster. And the algorithm learns to make these choices from being exposed to previous data collected with resultant outcomes with one of the two choices. 
So what we have actualy is:

<img align="center" width="500" height="300" src="perceptron.png">

$\mathcal{X} \subseteq \mathbb{R}^d$ and $d \in \mathbb{N}$ be the input space, and let $\mathcal{Y} = \{-1, 1\}$ 
 $x$: Input customer information that is used to make credit decision.
* $f:\mathcal{X} \rightarrow \mathcal{Y}$: *Unknown target* function that is the ideal formula for credit approval. 
* $\mathcal{X}$: *Input space* consisting of all possible input $x$.
* $\mathcal{Y}$: *Output space* consisting of no or yes credit approval.
* $\mathcal{D}$: *Data set* of tuples in  input-output examples of the form $(x_i, y_i)$, where $f(x_i) = y_i$ and $i \in \mathbb{N}$ .
* $\mathcal{A}$: Learning algorithm which uses $D$ to pick a formula (hypothesis) $g:\mathcal{X}\rightarrow \mathcal{Y}$ so that $g\approx f$, where $g\in \mathcal{H}$. Here $\mathcal{H}$ is the *hypothesis space*. 

For $h \in \mathcal{H}$, $h(x)$ gives different weights to the different coordinates of $x$. This reflects the relative importance of each coordinate to the credit decision. The combinded weighted coordinates form a credit score which is compared to some threshold, say $theta$. 

* Approve if
$$
\sum_{i=1}^{d}w_ix_i > \theta
$$

* Deny if
$$
\sum_{i=1}^{d}w_ix_i < \theta
$$

We next introduce a *bias* $- b = \theta$, and so, we build the following form for hypothesis functions in $\mathcal{H}$.

$$
h(x) = \text{sign}\Big((\sum_{i=1}^{d}w_ix_i) + b\Big), 
$$

where $h(x) = 1$ means approve and $h(x) = -1 $ means deny. 

We next simplify notation by treating the bias $b$ as a weight, and modify $x$ so that 

$$
w = [b, w_1, \dots, w_d]^{T}
$$

$$
x = [1.0, x_1, \dots, x_d]^{T}
$$

Thus, $\mathcal{X} = {1.0}\times\mathbb{R}^d$, and $h(x) = \text{sign}(w^{T}x)$. 

### Perceptron Learning Algorithm (PLA)
This is an iterative method. Suppose an example from $(x_1,y_1), \dots, (x_N, y_N)$ is currently misclassifed at time $t$, and denote this misclassifed example by $(x(t), y(t))$. Note that since $(x(t), y(t))$ is currently misclassifed, 

$$
y(t) \neq \text{sign}(w^{T}(t)x(t)). 
$$

**Update Rule:**

$$
w(t+1) = w(t) + y(t)x(t).
$$

**Theorem.** The perceptron model will always classify the training examples correctly when the data is linearly seperable. 
