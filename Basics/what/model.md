# 基本概念

目标：

- 知道每个概念的含义
- 每个参数对结果的影响
- 在有多种选择的情况下知道每个选项的优劣


## 构建模型


### convolutional layer

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


### activation function

用作激活函数的函数最好具有关于原点对称的性质

  - sigmoid

  - ReLU

#### 隐藏层的激活值分布

Q:各层的激活值的分布都要求有适当的广度？

A:因为通过在各层间传递多样性地数据，神经网络可以进行高校的学习。反过来，如果传递的是有所偏向的数据，就会出现梯度消失或者“表现力受限”的问题，导致学习可能无法顺利进行。

激活函数的选择不恰当带来的问题：

  - 梯度消失

  - 表现力受限


### batch normalization

[批量归一化-动手学深度学习](http://zh.diveintodeeplearning.org/chapter_convolutional-neural-networks/batch-norm.html)

引入动机： 为了使各层的激活值拥有适当的广度，“强制性”地调整激活值的分布。[1]

Pros:
 - 可以使学习快速进行(可以增大学习率)
 - 不那么依赖初始值（对于初始值不用那么神经质）
 - 抑制过拟合(降低Dropout等的必要性)

Q: 应该把BN层放在激活函数前面还是后面？[1]

A: *未完待续*

### fully connected

### softmax


## 训练模型

### train/valid/test split

[Splitting into train, dev and test sets](https://cs230-stanford.github.io/train-dev-test-split.html)

### weight initialization

[Deep Learning Best Practices — Weight Initialization](https://medium.com/usf-msds/deep-learning-best-practices-1-weight-initialization-14e5c0295b94)

[谷歌工程师：聊一聊深度学习的weight initialization](https://www.leiphone.com/news/201703/3qMp45aQtbxTdzmK.html)

[数值稳定性和模型初始化-动手学深度学习](http://zh.diveintodeeplearning.org/chapter_deep-learning-basics/numerical-stability-and-init.html)

- Initializing all weights to 0

  Q:为什么不能将权重初始值设为0？或者说为什么不能将权重初始值设为一样的值？[1]

  A:这是因为在误差反向传播法中，所有的权重值都将会进行相同的更新。比如，在2层神经网络中，假设第1层和第2层的权重为0。这样一来，正向传播时，因为输入层的权重为0,所以第2层的神经元全部会被传递相同的值。第2层的神经元中全部输入相同的值，这意味着反向传播时，第2层的权重全部都会进行相同的更新。因此，权重被更新为相同的值，并拥有了对称的值（重复的值）。这使得神经网络拥有许多不同的权重的意义丧失了。为了防止“权重均一化”（严格地讲，是为了瓦解权重的对称结构），必须随机生成初始值。[1]







常用的初始权重方法：

- Initializing weights randomly

- Xavier

  [Understanding Xavier Initialization In Deep Neural Networks](https://prateekvjoshi.com/2016/03/29/understanding-xavier-initialization-in-deep-neural-networks/)

  Xavier是以激活函数是线性函数为前提(sigmoid,tanh等S型曲线函数)而推倒出来的，因为sigmoid函数和tanh函数左右对称，且中央附近可以视作线性函数，所以适合使用Xavier初始值。

- He Init

  用于当激活函数使用ReLU时

- pre-trained

### learning rate(most important hyper-parameter)

- decay

### loss/cost/objective function

A loss function **is a part of a** cost function **which is a type of** an objective function.

[Objective function, cost function, loss function: are they the same thing?](https://stats.stackexchange.com/questions/179026/objective-function-cost-function-loss-function-are-they-the-same-thing)

[A list of cost functions used in neural networks, alongside applications](https://stats.stackexchange.com/questions/154879/a-list-of-cost-functions-used-in-neural-networks-alongside-applications)

Regression:

- MSE
- RMSE

Classification:

- Cross Entropy

- MAP

### batch size

### epochs



## 优化模型

[概览深度学习中的五大正则化方法和七大优化策略](https://juejin.im/post/5a40790151882512b72fe45e)

[Improving Neural Networks – Hyperparameter Tuning, Regularization, and More](https://www.analyticsvidhya.com/blog/2018/11/neural-networks-hyperparameter-tuning-regularization-deeplearning/)


### optimizer

- Gradient Descent

- SGD/Mini-Batch SGD

  Pros:

  简单，易实现

  Cons:

  如果函数的形状非均向(anisotropic),比如呈延伸状，搜索路的路径就会非常低效。*根本原因* 是，梯度的方向并没有指向最小值的方向。[1]

- Momentum

- AdaGrad

  AdaGrad会为参数的每个元素适当地调整学习率，于此同时进行学习。

  Pros:

  *未完待续*

  Cons:

  AdaGrad会记录过去所有梯度的平方和。因此，学习越深入，更新的幅度就越小。如果无止境地学习，更新量就会变为0,完全不再更新。[1]

- RMSProp

  为了改善AdaGrad不再更新的问题，提出了RMSProp方法。RMSProp方法并不是将过去所有的梯度一视同仁地相加，而是逐渐地遗忘过去的梯度，在做加法运算时将新梯度的信息更多地反映出来。这种操作从专业上讲，称为“指数移动平均”，呈指数函数式地减小过去的梯度的尺度。[1]

  Pors:

    *未完待续*

    Cons:

    *未完待续*




- Adam

  直观地说，将Momentum和AdaGrad两个方法融合。此外，进行超参数的"偏置校正"也是Adam的特征。

  Pors:

  *未完待续*

  Cons:

  *未完待续*




### regularization

[An Overview of Regularization Techniques in Deep Learning (with Python code)](https://www.analyticsvidhya.com/blog/2018/04/fundamentals-deep-learning-regularization-techniques/)

- early stopping

- dropout

- weight decay

  引入动机： 抑制过拟合、提高泛化能力的技巧[1]

  简单地说，权重衰减就是一种以减小权重参数的值为目的进行学习的方法。通过减小权重参数的值来抑制过拟合的发生。[1]

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

## Reference

[1] [《深度学习入门 基于Python的理论与实现》- 斋藤康毅](https://www.amazon.cn/dp/B07FDNSJ39/ref=sr_1_1?ie=UTF8&qid=1547102922&sr=8-1&keywords=%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E5%85%A5%E9%97%A8)
