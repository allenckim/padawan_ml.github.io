---
layout: post
category: cross-entropy softmax
date: 2017-04-12
---



# Gradient of Cross-Entropy Cost Function

During the impeleneting the Soft-max, Cross-Entropy cost function and its derivative, 

Let's start from the beginning.

In linear transform, the each input data $x^{(i)}$ is transformed by the $W$ as follows:
$$
h_\theta(x^{(i)}) = x^{(i)} W
$$
This score is transfomred to probability using the softmax function as follows:
$$
=\frac{e^{z_i}}{\sum_k^K e^{z_k}}
$$
Softmax function transforms the score of hypotheiss into the probability. Then we use the cross-entropy function as cost function.
$$
J(\theta) = \frac{1}{m} \sum_k^m 
$$
