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

![常数项](/2017/10/27/logistic-cost/c.png)

- 以 e 为底的指数求导公式

![e 为底的指数求导](/2017/10/27/logistic-cost/e.png)

- 对数复合求导公式

![对数复合求导公式](/2017/10/27/logistic-cost/log.png)

- 幂函数复合求导公式

![对数复合求导公式](/2017/10/27/logistic-cost/yx.png)

- 函数的和、差、积、商的求导法则

设 ![u](/2017/10/27/logistic-cost/u.png)，都可导，则

(1) ![和差求导](/2017/10/27/logistic-cost/v.png)

(2) ![乘积求导](/2017/10/27/logistic-cost/uv.png)

(3) ![常数乘函数](/2017/10/27/logistic-cost/cu.png)

(4) ![商求导](/2017/10/27/logistic-cost/uuv.png)
复合函数求导法则
 设 ![复合求导](/2017/10/27/logistic-cost/f1.png) 而![复合求导](/2017/10/27/logistic-cost/u1.png) 且![复合求导](/2017/10/27/logistic-cost/f.png)  及 ![复合求导](/2017/10/27/logistic-cost/x1.png) 都可导，则复合函数 ![复合求导](/2017/10/27/logistic-cost/c1.png)  的导数为

  ![复合求导](/2017/10/27/logistic-cost/fy.png)

  ## Logistic 回归的 Cost function 的推导过程：

之前采用的是梯度下降算法用来求函数的最小值。

  好吧，来吧正式开始了，有了以上的数学求导基础，接下来就容易多了，公式嘛，当初上学时，老师常说的一句话：“背过，记住！”


  ### Logistic回归的代价函数可以统一写成如下一个等式：

  ![Logistic回归的代价函数](/2017/10/27/logistic-cost/jlog.png)

其中：  
![sigmoid function](/2017/10/27/logistic-cost/tx.png)

![sigmoid function](/2017/10/27/logistic-cost/nr.png)

#### 下面开始我们的推导过程：如果要求![J](/2017/10/27/logistic-cost/J1.png) 对某一个参数![T](/2017/10/27/logistic-cost/T1.png) 的偏导数，则：

 - 1.根据求导公式，可以先把常数项 ![cm](/2017/10/27/logistic-cost/cm.png)提取出来，这样就只需要对求和符号内部的表达式求导，即：

## (1) ![K1](/2017/10/27/logistic-cost/K1.png)

其中 K(θ)' 为：
（为方便显示，先把右上角表示第i个样本的上标去掉）
![k3](/2017/10/27/logistic-cost/k3.png)

- 2.根据对数复合求导公式，![对数复合求导公式](/2017/10/27/logistic-cost/log.png)，对 K(θ)' 继续求导可得：

## (2) ![K](/2017/10/27/logistic-cost/K2.png)

之后 需要对 ![K](/2017/10/27/logistic-cost/H2.png)

现在 根据上面提到的

- 幂函数复合求导公式

![对数复合求导公式](/2017/10/27/logistic-cost/yx.png)

- 以 e 为底的指数求导公式

![e 为底的指数求导](/2017/10/27/logistic-cost/e.png)

先对![h0](/2017/10/27/logistic-cost/h0.png) 求导：

根据上面的已知公式：

![h1](/2017/10/27/logistic-cost/H1.png)

依据上面的商求导公式可得：

![h4](/2017/10/27/logistic-cost/h4.png)

![h5](/2017/10/27/logistic-cost/H5.png)

![h11](/2017/10/27/logistic-cost/h11.png)

![h12](/2017/10/27/logistic-cost/h12.png)

![h13](/2017/10/27/logistic-cost/h13.png)

### 将 (3) (4) 代入 (2) 中 ，可得：

![h14](/2017/10/27/logistic-cost/h14.png)

![h15](/2017/10/27/logistic-cost/h15.png)

![h16](/2017/10/27/logistic-cost/h16.png)

### 推导结果：
![h17](/2017/10/27/logistic-cost/h17.png)

#### 结论：Logistic Regression 的目的是 求解一组最佳拟合参数 θ 。这个求解的过程是由最优化算法完成的。
