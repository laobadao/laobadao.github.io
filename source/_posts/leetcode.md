---
title: Leetcode | Algorithm
date: 2017-11-14 09:34:10
tags:
  - Leetcode
  - Algorithm
categories: Algorithm
comments: true
---

## Hard
- [4. Median of Two Sorted Arrays]
[leetcode link](https://leetcode.com/problems/median-of-two-sorted-arrays/description/ )

  问题：给出的两个已经是排序好的数组,求中位数

  解决思路：[Divide and Conquer,Array,Binary Search][分治法，数组，二分法]
- [10. Regular Expression Matching] [leetcode link](https://leetcode.com/problems/regular-expression-matching/ )

### 【补充】DP - Dynamic Programming 动态规划：

#### Question: 什么是动态规划？动态规划的意义是什么？
[知乎原文链接](https://www.zhihu.com/question/23995189)

1. 动态规划的本质，是对问题状态的定义和状态转移方程的定义。

引自维基百科
>dynamic programming is a method for solving a complex problem by breaking it down into a collection of simpler subproblems.

动态规划是通过拆分问题，定义问题状态和状态之间的关系，使得问题能够以递推（或者说分治）的方式去解决。本题下的其他答案，大多都是在说递推的求解方法，**但如何拆分问题，才是动态规划的核心。而拆分问题，靠的就是状态的定义和状态转移方程的定义。**

>给定一个数列，长度为N，
求这个数列的最长上升（递增）子数列（LIS）的长度.
以 1 7 2 8 3 4为例。
>这个数列的最长递增子数列是 1 2 3 4，长度为4；
>次长的长度为3， 包括 1 7 8; 1 2 3 等.

**所以我们来重新定义这个问题：**

>给定一个数列，长度为N，
>设 F_{k} 为：以数列中第k项结尾的最长递增子序列的长度.
>求F_{1} .. F_{N} 中的最大值.

**动态规划方法要寻找符合“最优子结构“的状态和状态转移方程的定义，在找到之后，这个问题就可以以“记忆化地求解递推式”的方法来解决。而寻找到的定义，才是动态规划的本质。**

文艺的说，动态规划是寻找一种对问题的观察角度，让问题能够以递推（或者说分治）的方式去解决。寻找看问题的角度，才是动态规划中最耀眼的宝石！（大雾）

[知乎Link- 作者 王勐](https://www.zhihu.com/question/23995189/answer/35429905)

>怎么鉴定dp可解的一类问题需要从计算机是怎么工作的说起…计算机的本质是一个状态机，内存里存储的所有数据构成了当前的状态，CPU只能利用当前的状态计算出下一个状态（不要纠结硬盘之类的外部存储，就算考虑他们也只是扩大了状态的存储容量而已，并不能改变下一个状态只能从当前状态计算出来这一条铁律）

>当你企图使用计算机解决一个问题是，其实就是在思考如何将这个问题表达成状态（用哪些变量存储哪些数据）以及如何在状态中转移（怎样根据一些变量计算出另一些变量）。**所以所谓的空间复杂度就是为了支持你的计算所必需存储的状态最多有多少，所谓时间复杂度就是从初始状态到达最终状态中间需要多少步**！

### DP方程

### LIS(i) = max{LIS(j)+1} j<i and a[j]<a[i]

- 所以一个问题是该用递推、贪心、搜索还是动态规划，完全是由这个问题本身阶段间状态的转移方式决定的！
- 每个阶段只有一个状态->递推；
- 每个阶段的最优状态都是由上一个阶段的最优状态得到的->贪心；
- 每个阶段的最优状态是由之前所有阶段的状态的组合得到的->搜索；
- **每个阶段的最优状态可以从之前某个阶段的某个或某些状态直接得到而不管之前这个状态是如何得到的->动态规划。**

>每个阶段的最优状态可以从之前某个阶段的某个或某些状态直接得到--这个性质叫做 **最优子结构；**
>而不管之前这个状态是如何得到的--这个性质叫做 **无后效性。**


**个人理解：1.给问题找到某种分界状态（最优子结构），if else ,对状态 满足或不满足，给出定义。
2.在有了自己定义的状态的基础之上，在编写状态方程，分界边界两边的关系，满足不满足的 等式或不等式情况。
3.然后就找到了适合的递推关系式。
状态转移方程，就是定义了问题和子问题之间的关系。
可以看出，状态转移方程就是带有条件的递推式。**


### 对于[ 10. Regular Expression Matching] 这个问题：

Some examples:

isMatch(“aa”,”a”) → false “aa” 俩字母 ，”a”一个字母
 aa 不符合 a 这个正则表达式

isMatch(“aa”,”aa”) → true

isMatch(“aaa”,”aa”) → false

isMatch(“aa”, “a*”) → true “aa” 符合 a* ,开头字母是 a 后面的字母任意

isMatch(“aa”, “.* ”) → true

isMatch(“ab”, “.* ”) → true

isMatch(“aab”, “c*a*b”) → true

### 方法 1：Recursion 递归

```python
class Solution(object):
    def isMatch(self, text, pattern):
        if not pattern:
            return not text

        first_match = bool(text) and pattern[0] in {text[0], '.'}

        if len(pattern) >= 2 and pattern[1] == '*':
            return (self.isMatch(text, pattern[2:]) or
                    first_match and self.isMatch(text[1:], pattern))
        else:
            return first_match and self.isMatch(text[1:], pattern[1:])
```

```java
class Solution {
    public boolean isMatch(String text, String pattern) {
        if (pattern.isEmpty()) return text.isEmpty();
        boolean first_match = (!text.isEmpty() &&
                               (pattern.charAt(0) == text.charAt(0) || pattern.charAt(0) == '.'));

        if (pattern.length() >= 2 && pattern.charAt(1) == '*'){
            return (isMatch(text, pattern.substring(2)) ||
                    (first_match && isMatch(text.substring(1), pattern)));
        } else {
            return first_match && isMatch(text.substring(1), pattern.substring(1));
        }
    }
}
```

\[
e ^ { 2 }
\]

#### Complexity Analysis： 复杂度分析

  + Time Complexity: 时间复杂度

  Let T,P be the lengths of the text and the pattern respectively.（让 T,P 分别代表 text 和 pattern 的长度），In the worst case, a call to **match(text[i:], pattern[2j:])** will be made  times, （最糟糕的情况，调用 match（）方法 ）
 and strings of the order O(T - i)O(T−i) and O(P - 2*j)O(P−2∗j)
will be made. Thus, the complexity has the order

. With some effort outside the scope of this article,
we can show this is bounded by

$ sigmoid(x)= \frac {1}{1+ e^ {-x }}$
