---
title: 机器学习实战 | Logistic Regression
date: 2017-10-25 10:17:46
tags:
  - Machine Learning
categories: Machine Learning
---
## Logistic 回归

- 解决二分类问题。 是或不是 yes/no 1/0

- Sigmoid 函数

- 为了实现 Logistic 回归分类器，我们可以在每个特征上都乘以一个回归系数，然后把所有的结果值相加，将这个总和代入 Sigmoid 函数中，进而得到一个范围在0~1之间的数值。

- 梯度上升算法用来求函数的最大值，而梯度下降算法用来求函数的最小值。

- Logistic回归是回归的一种方法，它利用的是Sigmoid函数阈值在[0,1]这个特性。Logistic回归进行分类的主要思想是：根据现有数据对分类边界线建立回归公式，以此进行分类。其实，Logistic本质上是一个基于条件概率的判别模型(Discriminative Model)。

### 数学基础

- 常数的导数是 0。

- 分数求导 f=U/V , f'=(U'V-V'U)/V^2

- ![求导公式](logistic-regression/y.png)

- y=e^(-x)

 y'=e^(-x) * (-x)'

   =-e^(-x)

   复合函数求导

- 对数复合函数求导

- 幂数复合函数求导
