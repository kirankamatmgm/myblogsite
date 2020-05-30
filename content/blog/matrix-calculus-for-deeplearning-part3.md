---
path: Matrix Calculus Part3
date: 2020-05-30T01:54:32.374Z
title: Matrix Calculus for DeepLearning (Part3)
description: >-
  This is last part of blog, which explains The gradient of the neural network
  activation and loss function, and wind up blog
---
We have looked into Jacobian matrix, element wise operation, derivatives involving single expressions and vector sum reduction and chain rule in previous blog. Please through that, [Blog 1](https://kirankamath.netlify.app/blog/matrix-calculus-for-deeplearning-part1/), [Blog 2](https://kirankamath.netlify.app/blog/matrix-calculus-for-deeplearning-part2/). 

## The gradient of neuron activation

Let us compute the derivative of a typical neuron activation for a single neural network computation unit with respect to the model parameters, _w_ and b

_activation_(**x**) = max(0, **w** . **x** + b)

This represents neuron with fully connected weights and relu. 

Let us compute derivative of  ( **w** . **x** + b ) wrt **w** and b

dot product **w . x** is summation of element wise multiplication of elements. Partial derivative of sum(**w** ⊗ **x**) can be calculated using chain rule using intermediate vector variable

![activation](/assets/blog11img1.png)

The above image use of the max(0, z) function call on scalar z just says to treat all negative z values as 0. The derivative of the max function is a piecewise function. When z ≤ 0, the derivative is 0 because z is a constant. When z > 0, the derivative of the max function is just the derivative of z, which is 1.

When the activation function clips affine function output z to 0, the derivative is zero with respect to any weight w i . When z > 0, it’s as if the max function disappears and we get just the derivative of z with respect to the weights.

## The gradient of the neural network loss function



\# **Blog 11**