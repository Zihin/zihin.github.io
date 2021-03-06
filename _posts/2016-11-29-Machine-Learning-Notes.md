---
layout:     post
title:      "Machine Learning Notes"
tags:       [Machine Learning]
categories: [Machine Learning]
---

# 第1章

## Basics

### **独立同分布(Independent and identically distributed, IID, i.i.d.)**

In probability theory and statistics, a sequence or other collection of random variables is independent and identically distributed (i.i.d.) <u>if each random variable has the ***same probability distribution*** as the others and all are ***mutually independent***</u>. 

> 如实验条件保持不变，一系列的抛硬币的正反面结果是独立同分布。

### **No Free Lunch Theorem**

针对某一具体域内的所有优化问题Q，算法A与算法B经过m步迭代之后达到目标函数给定值的所有可能性的累加和是相等的。

> 在一定的前提下，所有学习算法的期望性能都跟随机胡猜差不多。

![From Wikipedia](http://ofqz295wv.bkt.clouddn.com/public/16-11-29/14951989.jpg)

假设有A、B两种任意（随机或确定）算法，对于所有问题集，它们的平均性能是相同的（性能可采用多种方法度量，如最优解、收敛速率等）。

### **NP难题**

​	在一个周六的晚上，你参加了一个盛大的晚会。由于感到局促不安，你想知道这一大厅中是否有你已经认识的人。你的主人向你提议说，你一定认识那位正在甜点盘附近角落的女士罗丝。不费一秒钟，你就能向那里扫视，并且发现你的主人是正确的。然而，如果没有这样的暗示，你就必须环顾整个大厅，一个个地审视每一个人，看是否有你认识的人。

​	生成问题的一个解通常比验证一个给定的解时间花费要多得多。这是这种一般现象的一个例子。与此类似的是，如果某人告诉你，数$13717421$可以写成两个较小的数的乘积，你可能不知道是否应该相信他，但是如果他告诉你他可以因式分解为$3607\times3803$，那么你就可以用一个袖珍计算器容易验证这是对的。人们发现，所有的完全多项式非确定性问题，都可以转换为一类叫做满足性问题的逻辑运算问题。既然这类问题的所有可能答案，都可以在多项式时间内计算，人们于是就猜想，是否这类问题，存在一个确定性算法，可以在多项式时间内，直接算出或是搜寻出正确的答案呢？这就是著名的NP=P？的猜想。 不管我们编写程序是否灵巧，判定一个答案是可以很快利用内部知识来验证，还是没有这样的提示而需要花费大量时间来求解，被看作逻辑和计算机科学中最突出的问题之一。

> 首先这些p和np都是用来描述解决一个问题需要的时间和它输入规模之间的关系。
>
> **P问题**
>
> 一个问题可以在多项式$O(n^k)$的时间复杂度内解决。
>
> 例如：n个数的排序（不超过$O(n^2)$）
>
> **NP问题**
>
> 一个问题的解可以在多项式的时间内被证实或证伪。
>
> 例如：典型的子集求和问题,给定一个整数集合求是否存在一个非空子集它的和为零。如给定集合$S= \{-1,3,2,-5,6\}$，很明显子集$\{3,2,-5\}$能满足问题，并且验证该解只需要线性时间复杂度就能被证实。
>
> **NP-hard问题：**
>
> 任意np问题都可以在多项式时间内归约为该问题。归约的意思是为了解决问题A，先将问题A归约为另一个问题B，解决问题B同时也间接解决了问题A。
>
> 例如，停机问题。
>
> **NPC问题**
>
> 既是NP问题，也是NP-hard问题。
>
> 例如，SAT问题（第一个NPC问题）。该问题的基本意思是，给定一系列布尔变量以及它的约束集，是否存在一个解使得它的输出为真。
>
> **相互关系：**
>
> 显然，所有P问题都是NP问题，反之则不一定。npc问题是np问题的子集，也是p问题和np问题的差异所在。如果找到一个多项式内能被解决的npc问题的解决方法，那么P=NP。


![img](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/P_np_np-complete_np-hard.svg/600px-P_np_np-complete_np-hard.svg.png)



[什么是P问题、NP问题和NPC问题](http://www.matrix67.com/blog/archives/105)

[怎么理解 P 问题和 NP 问题？](https://www.zhihu.com/question/27039635)

### **BP算法**



### **异或(Exclusive or, XOR)**

异或也叫半加运算，其运算法则相当于不带进位的二进制加法：二进制下用1表示真，0表示假，则异或的运算法则为：0⊕0=0，1⊕0=1，0⊕1=1，1⊕1=0（同为0，异为1），这些法则与加法是相同的，只是不带进位。

> exclusive or 就是exclusive（排除）a and b这个种情况。

| Input A | Input B | Output |
| :-----: | :-----: | :----: |
|    1    |    1    |   0    |
|    1    |    0    |   1    |
|    0    |    1    |   1    |
|    0    |    0    |   0    |



## More

### **The Halting Problem**

In computability theory, the halting problem is the problem of determining, from a description of an arbitrary computer program and an input, whether the program will finish running or continue to run forever.

> 从前有家饭店，只卖包子和馒头，这时候假设存在一个聪明的侍者，这个侍者可以判断任何一个前来点餐的客人要点什么菜，这时候有个腹黑的家伙说：
>
> “如果你判断我要点包子，那我就点馒头；如果你判断我点馒头，那我就吃包子。”
>
> 那么显然这是矛盾的，所以不存在这样的侍者。
>
> 这个例子与停机问题大致上是相通的。侍者就是停机问题中那个用来判断别的程序是否停机的程序，而包子和馒头对应停机与不停机的状态。

[不可解问题(Undecidable Decision Problem)](http://www.matrix67.com/blog/archives/55)

[停机问题、Chaitin常数与万能证明方法](http://www.matrix67.com/blog/archives/901)

[See Proof in Youku Video](http://v.youku.com/v_show/id_XMTYxMjM5ODYyMA==.html#paction)

