# 基本概念

目标：

- 知道每个概念的含义
- 没个参数对结果的影响
- 在有多种选择的情况下知道每个选项的优劣


## 构建模型

### 选择layer

#### convolutional layer

- conv

  - kernel size

  - stride

  - padding

    - SAME

    - VALID

- pooling

  - stride

  - average

  - max


#### activation function

  - sigmoid

  - ReLU

  - softmax

#### batch normalization

[批量归一化-动手学深度学习](http://zh.diveintodeeplearning.org/chapter_convolutional-neural-networks/batch-norm.html)

#### fully connected




## 训练模型

### weight initialization

[Deep Learning Best Practices — Weight Initialization](https://medium.com/usf-msds/deep-learning-best-practices-1-weight-initialization-14e5c0295b94)

[谷歌工程师：聊一聊深度学习的weight initialization](https://www.leiphone.com/news/201703/3qMp45aQtbxTdzmK.html)

[数值稳定性和模型初始化-动手学深度学习](http://zh.diveintodeeplearning.org/chapter_deep-learning-basics/numerical-stability-and-init.html)

- Initializing all weights to 0

- Initializing weights randomly

- Xavier

  [Understanding Xavier Initialization In Deep Neural Networks](https://prateekvjoshi.com/2016/03/29/understanding-xavier-initialization-in-deep-neural-networks/)

- pre-trained

### batch size

### epochs

### learning rate

- decay

### loss/cost/objective function

A loss function **is a part of a** cost function **which is a type of** an objective function.

[Objective function, cost function, loss function: are they the same thing?](https://stats.stackexchange.com/questions/179026/objective-function-cost-function-loss-function-are-they-the-same-thing)

[A list of cost functions used in neural networks, alongside applications](https://stats.stackexchange.com/questions/154879/a-list-of-cost-functions-used-in-neural-networks-alongside-applications)

### train/valid/test split

[Splitting into train, dev and test sets](https://cs230-stanford.github.io/train-dev-test-split.html)

## 优化模型

[概览深度学习中的五大正则化方法和七大优化策略](https://juejin.im/post/5a40790151882512b72fe45e)

[Improving Neural Networks – Hyperparameter Tuning, Regularization, and More](https://www.analyticsvidhya.com/blog/2018/11/neural-networks-hyperparameter-tuning-regularization-deeplearning/)


### optimizer

- gradient descent

- SGD

- Momentum

- Mini-Batch SGD

- Adam

- RMSProp


### regularization

[An Overview of Regularization Techniques in Deep Learning (with Python code)](https://www.analyticsvidhya.com/blog/2018/04/fundamentals-deep-learning-regularization-techniques/)

- early stopping

- dropout

- data augmentation

- L2/L1 regularization

- ensemble


## 评估模型

### total parameters

### complexity

- FLOPs

## 常见问题

[数值稳定性和模型初始化-动手学深度学习](http://zh.diveintodeeplearning.org/chapter_deep-learning-basics/numerical-stability-and-init.html)

- overfitting / underfitting

- vanishing gradient

- exploding gradient
