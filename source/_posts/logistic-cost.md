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

- 函数的和、差、积、商的求导法则

设 ![u](/logistic-cost/u.png)，都可导，则

(1) ![和差求导](/logistic-cost/v.png)

(2) ![乘积求导](/logistic-cost/uv.png)

(3) ![常数乘函数](/logistic-cost/cu.png)

(4) ![商求导](/logistic-cost/uuv.png)

 - 复合函数求导法则

 设 ![复合求导](/logistic-cost/f1.png) 而![复合求导](/logistic-cost/u1.png) 且![复合求导](/logistic-cost/f.png)  及 ![复合求导](/logistic-cost/x1.png) 都可导，则复合函数 ![复合求导](/logistic-cost/c1.png)  的导数为

  ![复合求导](/logistic-cost/fy.png)
