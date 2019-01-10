# 论文笔记

当我在读*Deep Residual Learning for Image Recognition*这篇文章的时候，我发现了一些之前很疑惑的概念，在这篇文章中都有提到，并且还有原始论文出处，下面把这些概念和论文引用列出来：

## vanishing/exploding gradients


> Driven by the significance of depth, a question arises: Is learning better networks as easy as stacking more layers?
> An obstacle to answering this question was the notorious problem of vanishing/exploding gradients [14, 1, 8], which hamper convergence from the beginning.
> This problem, however, has been largely addressed by normalized initialization [23, 8, 36, 12] and intermediate normalization layers [16], which enable networks with tens of layers to start converging for stochastic gradient descent (SGD) with backpropagation [22].


[14] S. Hochreiter. Untersuchungen zu dynamischen neuronalen netzen.
Diploma thesis, TU Munich, 1991

[1] Y. Bengio, P. Simard, and P. Frasconi. Learning long-term dependencies with gradient descent is difficult. IEEE Transactions on Neural
Networks, 5(2):157–166, 1994.

[8] [X. Glorot and Y. Bengio. Understanding the difficulty of training
deep feedforward neural networks. In AISTATS, 2010.](http://proceedings.mlr.press/v9/glorot10a/glorot10a.pdf)

## degradation

> When deeper networks are able to start converging, a degradation problem has been exposed: with the network depth increasing, accuracy gets saturated (which might be unsurprising) and then degrades rapidly.
> Unexpectedly, such degradation is not caused by overfitting, and adding more layers to a suitably deep model leads to higher training error, as reported in [10, 41] and thoroughly verified by our experiments. Fig. 1 shows a typical example.


## batch normalization

> We adopt batch normalization (BN) [16] right after each convolution and before activation, following [16].

> We argue that this optimization difficulty is unlikely to
be caused by vanishing gradients. These plain networks are
trained with BN [16], which ensures forward propagated
signals to have non-zero variances. We also verify that the
backward propagated gradients exhibit healthy norms with
BN. So neither forward nor backward signals vanish.

[16] [S. Ioffe and C. Szegedy. Batch normalization: Accelerating deep network training by reducing internal covariate shift. In ICML, 2015.](http://proceedings.mlr.press/v37/ioffe15.pdf)

## mini-batch

>  We use SGD with a mini-batch size of 256.

## FLOPs - complexity

[How to understand / calculate FLOPs of the neural network model?](https://stats.stackexchange.com/questions/291843/how-to-understand-calculate-flops-of-the-neural-network-model)

###   参考资料

[Understanding and Implementing Architectures of ResNet and ResNeXt for state-of-the-art Image Classification: From Microsoft to Facebook [Part 1]](https://medium.com/@14prakash/understanding-and-implementing-architectures-of-resnet-and-resnext-for-state-of-the-art-image-cf51669e1624)
