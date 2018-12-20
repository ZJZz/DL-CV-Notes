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
