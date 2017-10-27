---
title: Logistic回归-代价函数求导过程 | 内含数学相关基础
date: 2017-10-27 10:21:32
tags:
  - Machine Learning
  - Logistic Regression
  - Cost Function
categories: Machine Learning
comments: true
---

## 相关函数求导公式

  先复习回顾下一些数学基础，帮助推导过程可以更好的理解。下面列举的公式都是，接下来的推导中会用到的，没有涉及到的公式，此处不再列举。

- 常数项求导

![常数项](/logistic-cost/c.png)

- 以 e 为底的指数求导公式

![e 为底的指数求导](/logistic-cost/e.png)

- 对数复合求导公式

![对数复合求导公式](/logistic-cost/log.png)

- 幂函数复合求导公式

![对数复合求导公式](/logistic-cost/yx.png)

- 函数的和、差、积、商的求导法则

设 ![u](/logistic-cost/u.png)，都可导，则

(1) ![和差求导](/logistic-cost/v.png)

(2) ![乘积求导](/logistic-cost/uv.png)

(3) ![常数乘函数](/logistic-cost/cu.png)

(4) ![商求导](/logistic-cost/uuv.png)
 - 复合函数求导法则

 设 ![复合求导](/logistic-cost/f1.png) 而![复合求导](/logistic-cost/u1.png) 且![复合求导](/logistic-cost/f.png)  及 ![复合求导](/logistic-cost/x1.png) 都可导，则复合函数 ![复合求导](/logistic-cost/c1.png)  的导数为

  ![复合求导](/logistic-cost/fy.png)


  ## Logistic 回归的 Cost function 的推导过程：

之前采用的是梯度下降算法用来求函数的最小值。

  好吧，来吧正式开始了，有了以上的数学求导基础，接下来就容易多了，公式嘛，当初上学时，老师常说的一句话：“背过，记住！”


  #### Logistic回归的代价函数可以统一写成如下一个等式：

  ![Logistic回归的代价函数](/logistic-cost/jlog.png)

其中：  
![sigmoid function](/logistic-cost/tx.png)

![sigmoid function](/logistic-cost/nr.png)
