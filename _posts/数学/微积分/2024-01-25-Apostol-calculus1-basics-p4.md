---
title: Apostol微积分Ⅰ基础篇P4 数学归纳法
date: 2024-01-25 22:37:17 +0800
categories: [数学,微积分]
tags: [微积分基础，证明方法]
---

## I  4.1 用数学归纳法证明的一个例子

当我们对整数$k$ 加1时总能得到更大的整数$k+1$, 所以不存在最大的整数。然而从数$1$开始，连续地通过有限个加1的步骤，每步从$k$ 到$k+1$, 我们可以取得任意大的正整数。这就是被数学家称为归纳证法 (**proof by induction**) 的一类推理的基础。我们通过第1节中计算抛物线弓形面 (parabolic segment) 的面积所用到的不等式：
$$
1^2+2^2+\cdots + (n-1)^2 < \dfrac{n^3}{3} < 1^2+2^2+\cdots +n^2  \tag{I.19}
$$


来说明归纳证法的用法。我们先考虑左边的不等式，记为$A(n)$ (包含变量$n$的断言).   对于最前面几个$n$值，很容易验证这个断言成立，例如取$n = 1, 2, 3$, 断言变为：
$$
A(1): 0<\dfrac{1^3}{3},\quad A(2):1^2<\dfrac{2^3}{3},\quad A(3): 1^2+2^2<\dfrac{3^3}{3}
$$



当 $n=1$ 时我们把左边的和解释为0.     
我们的目标是证明对所有正整数$n$, 断言$A(n)$都为真。假设已经证明对某个$n$值$A(n)$ 为真，比如$n=k$ 时，  我们已经证明：


$$
A(k): 1^2+2^2+\cdots +(k-1)^2 < \dfrac{k^3}{3}
$$


对固定的正整数$k\ge1$ 成立。利用这个假设，我们要证明$n=k+1$时对应的结论


$$
A(k+1): 1^2+2^2+\cdots +k^2 < \dfrac{(k+1)^3}{3}
$$


也成立。

我们发现对$A(k)$ 两边加$k^2$ 得到不等式：


$$
1^2+2^2+\cdots +(k-1)^2 + k^2 < \dfrac{k^3}{3}+k^2
$$


为了推出$A(k+1)$ 的结论，只须证：  


$$
\dfrac{k^3}{3}+k^2 < \dfrac{(k+1)^3}{3}
$$



展开右边


$$
\dfrac{(k+1)^3}{3} = \dfrac{k^3+3k^2+3k+1}{3} = \dfrac{k^3}{3}+k^2+k+\dfrac{1}{3}
$$


即可直接推出须证的不等式。至此我们已经证明了从$A(k)$ 可以推出 $A(k+1)$.  现在$A(1)$ 已直接验证为真，因此$A(2)$ 也为真。当$A(2)$ 为真时$A(3)$ 也为真.  以此类推，我们可以证明$A(n)$对所有正整数$n$都为真。于是$I.19$ 左边的不等式成立。同理可证右边的不等式。

## I 4.2 数学归纳法的原理

读者应该确保能够理解上述归纳证明的模式。首先我们证明断言$A(n)$ 在$n=1$ 时成立，然后我们证明如果断言对某个特定的正整数成立，那么对下一个正整数断言也成立。由此我们得出断言对所有正整数成立的结论。  
归纳法的思想可以用许多非数学的方式来说明。The domino effect is a good analogy for mathematical induction. 例如，设想一排玩具士兵顺序地编上号码，并且假定它们排列得如此紧密，以致如果其中任何一个，比方说编号为$k$的一个倒下，就将碰倒编号为$k+1$的下一个士兵。那么，任何人都能够想象，如果编号为1的士兵向后倒下，将会发生什么情况，同样显然的是，如果一个后面的士兵首先被碰倒，比方说其编码为$n_1$，则所有在它之后的士兵都将倒下。这是对数学归纳法稍进一步的推广，可用下列方式叙述：

**归纳证明的方法**  令$A(n)$ 是关于整数$n$ 的一个断言，如果我们能完成以下两个步骤，就能证明$A(n)$对所有$n\ge n_1$ 都为真：   
$(a)$  证明$A(n_1)$ 为真.   
$(b)$  令$k$ 为任意$\ge n_1$ 的固定整数. 假设$A(k)$ 为真并证明$A(k+1)$ 也为真.

在实际应用中通常$n_1 = 1$ ， 归纳证法的逻辑证明是下述关于实数的定理：

**定理I.36 数学归纳法原理**  令$S$ 是一个正整数集合，如果这个集合满足以下两个性质：  
$(a)$ 数$1$在集合中  
$(b)$ 如果正整数$k$ 在$S$ 中，则$k+1$ 也在$S$ 中.     
则每个正整数都在集合$S$ 中。

**证明：** 性质$(a)$和$(b)$告诉我们$S$是一个归纳集。我们在$I  3.6$节中用最小归纳集来定义全体正整数集，即每一个归纳集都包含全体正整数集，所以$S$ 包含了所有正整数。   
每当我们用数学归纳法证明断言$A(n)$ 对所有$n \ge1$  都成立时，我们正是在把定理$I.36$ 应用到使得$A(n)$ 成立的所有正整数的集合。如果我们想证明仅当$n \ge n_1$ 时$A(n)$ 成立，就改一下断言中的变量，把定理$I.36$ 应用到使得$A(n+n_1-1)$  成立的所有正整数$n$ 的集合.  (当$n\ge1$ 时$n+n_1-1 \ge n_1$)

## I 4.3 良序原理

正整数还有另一个重要的性质叫做良序原理，也被用作归纳证法的基础。

> **定理I.37 良序原理**  每个非空正整数集都有最小元.

注意良序原理仅适用于正整数集，对任意整数集并不成立。例如，全部整数的集合$\mathbb{Z}$ 没有最小元。  

良序原理可以从归纳法原理推导出来。下一节$I 4.5$会给出证明过程.  这一节的最后我们用以下例子来说明如何用良序原理来证明关于正整数的定理。

令$A(n)$ 表示以下断言:



$$
A(n): 1^2+2^2+\cdots + n^2 = \dfrac{n^3}{3} + \dfrac{n^2}{2} + \dfrac{n}{6}
$$


我们再次注意到很容易验证$A(1)$ 为真：


$$
A(1): 1^2 =  \dfrac{1^3}{3}+ \dfrac{1^2}{2}+\dfrac{1}{6}
$$



现在只有两种可能：  
$(\mathrm{i})$ $A(n)$ 对所有正整数$n$都成立.  

$(\mathrm{ii})$ 至少存在一个正整数$n$ 使得$A(n)$ 为假.

我们要证明$(\mathrm{ii})$ 会导致一个矛盾。假设$(ii)$ 成立，我们把良序原理应用到使得$A(n)$ 为假的所有正整数的集合。 这个正整数集是非空的。根据良序原理，存在一个最小的正整数$k$ 使得$A(k)$ 为假.  因为$A(1)$ 为真，这个$k$ 必然大于1.  因为$k$是使得$A(k)$ 为假的最小整数，所以断言$A(k-1)$ 必然为真，即



$$
A(k-1):\ 1^2+2^2+\cdots+(k-1)^2 = \dfrac{(k-1)^3}{3} + \dfrac{(k-1)^2}{2} + \dfrac{k-1}{6}
$$



一定成立。两边加$k^2$ 有：



$$
\require{enclose}
\begin{align}
1^2+2^2+\cdots+k^2 &= \dfrac{k^3+3k^2(-1)+3k(-1)^2+(-1)^3}{3} + \dfrac{k^2-2k+1}{2}+k^2+\dfrac{k-1}{6} \\
&= \dfrac{k^3-3k^2+3k-1}{3}+\dfrac{k^2-2k+1}{2} + k^2 + \dfrac{k-1}{6} \\
&= \dfrac{k^3}{3} \enclose{horizontalstrike}{-k^2} \enclose{horizontalstrike}{+k}-\dfrac{1}{3} +\dfrac{k^2}{2}\enclose{horizontalstrike}{-k}+\dfrac{1}{2} + \enclose{horizontalstrike}{k^2} +\dfrac{k}{6}-\dfrac{1}{6} \\
&=\dfrac{k^3}{3}+\dfrac{k^2}{2}+\dfrac{k}{6}
\end{align}
$$


这个等式说明$A(k)$为真，与$k$是使得$A(k)$ 为假的整数矛盾,  假设$(\mathrm{ii})$ 不成立. 所以$(i)$成立。这就证明了前$n$个自然数的平方和公式对$n\ge 1$ 都成立. 这个恒等式的直接推论就是$(I.19)$ 右边的不等式.    
这种利用良序原理的证法也称为归纳证法，当然归纳证法更常见的形式是先验证$A(1)$ 成立，再证明从$A(k)$ 能推出$A(k+1)$. 

## I 4.5 良序原理的证明

这一节我们将从数学归纳法原理推出良序原理。  
令$T$是一个非空正整数集，我们想要证明$T$有最小元. 即证明$T$中存在一个正整数$t_0$, 使得$t_0 \le t$ 对所有$t \in T$ 都成立.  
假设$T$没有最小元. 我们要证明这会推出一个矛盾。正整数$1$不能在$T$中. (否则$1$就是$T$的最小元) . 令$S$ 表示对所有$t \in T$ 都满足$n < t$ 的所有正整数$n$的集合.  因为$1 < t$ 对所有$t \in T$ 都成立，所以$1$ 在$S$ 中. 接下来，令$k$是$S$中的一个正整数，我们要证明$k+1$也在$S$ 中. 假设$k+1$不在$S$中，则根据$S$的定义，存在某个$t_1 \in T$, 使得$t_1 \le k+1$. 因为$T$ 没有最小元，$T$ 中必存在某个正整数$t_2 < t_1$ ，则$t_2 < k+1$,  但这意味着$t_2 \le k$. 这与$T$中所有数都大于$S$中所有数矛盾。所以$k+1$ 也在$S$中. $S$满足归纳集的定义,  根据数学归纳法原理，$S$包含所有的正整数。因为$T$是非空正整数集，则$T$中至少存在一个正整数$t$，然而这个$t$ 也在$S$中，根据$S$的定义就会导致$t < t$ 这样一个矛盾。因此，$T$没有最小元的假设不成立，即$T$ 必有最小元。这样就用数学归纳法原理证明了良序原理。

## I 4.6 求和记号

计算抛物线弓形面积时，我们遇到了这个和：


$$
1^2+2^2+3^2+\cdots +n^2  \tag{I.20}
$$


注意到一般项的形式是$k^2$ , 通过让$k$取遍值$1,2,3,\cdots n$ 我们就得到了所有的项。有一个有用且方便的记号，使我们能把这类和写成更简洁的形式。这个记号叫做求和记号，用希腊字母 $\sum$ (Sigma) 来表示. 使用求和记号，我们可以把$(I.20)$ 中的和记为：


$$
\sum_{k=1}^{n} k^2
$$


这个记法读作“对$k$取$1$到$n$的$k^2$的和” (The sum of $k^2$ for $k$ running from $1$ to $n$) .  sigma符号上下方的数字告诉我们$k$的取值范围。字母$k$被称为求和指标 (index of summation) .  当然，变量名用什么字母表示并不重要，$k$ 可以用任何方便的字母来替换，例如，除了$\sum \limits_{k=1}^n k^2$ 我们可以用$\sum \limits_{i=1}^{n} i^2$,  $\sum \limits_{j=1}^n j^2$, $\sum \limits_{m=1}^n m^2$ 等等可选的记号来表示同一个和式.  以这种方式使用的$i,j,k.m$ 等字母被称为哑指标 (dummy indices). 在这个例子中，字母$n$已经被用来表示项数，所以$n$不适合作为哑指标.  

更一般地，当我们想要构造若干实数的和，比如$a_1,\cdots,a_n$， 我们用以下记号来表示这样的和：  


$$
a_1 + a_2 + \cdots + a_n  \tag{I.21}
$$


用求和记号表示如下：


$$
\sum\limits_{k=1}^n a_k  \tag{I.22}
$$



例如：


$$
\begin{align}
\sum \limits_{k=1}^4 a_k &=  a_1+ a_2+a_3+a_4 \\
\sum \limits_{i=1}^5 x_i &= x_1 + x_2 + x_3 +x_4 + x_5
\end{align}
$$



有时从$0$ 或从某个大于$1$的指标开始求和更方便，例如：


$$
\begin{align}
\sum \limits_{i=0}^4 x_i &= x_0 + x_1 + x_2 + x_3 + x_4 \\
\sum \limits_{n=2}^5 n^3 &= 2^3 + 3^3 + 4^3 + 5^3
\end{align}
$$


求和记号的其他用法举例如下:  


$$
\begin{align}
\sum \limits_{m=0}^4 x^{m+1} &= x + x^2 + x^3 + x^4 + x^5 \\
\sum \limits_{j=1}^6 2^{j-1} &= 1 + 2 + 2^2 + 2^3 + 2^4 + 2^5
\end{align}
$$



再次强调哑指标的选择不重要。我们注意到最后一个和也可以写成以下形式：


$$
\sum \limits_{q=1}^6 2^{q-1} = \sum\limits_{r=0}^5 2^r = \sum\limits_{n=0}^5 2^{5-n} = \sum\limits_{k=1}^6 2^{6-k}
$$



注：从严格的逻辑观点来看，$(I.21)$ 和$(I.22)$ 中的符号并不属于实数系的原始符号。为了论述更严谨，我们可以根据原始符号来定义这些新符号。这可以通过一个叫做归纳法定义(definition by induction)的过程来完成。归纳法定义类似归纳证明，由两部分组成：

$(a)$ 我们定义    


$$
\sum \limits_{k=1}^{1} a_k = a_1
$$


$(b)$ 假设对固定$n \ge 1$ 我们已经定义了$\sum \limits_{k=1}^n a_k$ , 我们进一步定义


$$
\sum \limits_{k=1}^{n+1} a_k = \sum \limits_{k=1}^n a_k + a_{n+1}
$$


在$(b)$ 中令$n=1$ , 由$(a)$ 可得：


$$
\sum \limits_{k=1}^2 a_k = \sum \limits_{k=1}^{1} a_k + a_{n+1} = a_1 + a_2
$$


现在已经定义了$\sum \limits_{k=1}^2 a_k$ , 令$(b)$ 中$n=2$ 可得：


$$
\sum \limits_{k=1}^{3} a_k = \sum \limits_{k=1}^{2} a_k + a_3 = (a_1+a_2) + a_3
$$



根据加法结合律 (实数系域公理2)， 和$(a_1+a_2) + a_3$与$a_1+(a_2+a_3)$ 相同，因此我们可以省略掉括号而不产生歧义。于是我们定义了 $\sum \limits_{k=1}^{3} = a_1+a_2+a_3$.  类似地，我们有：


$$
\sum \limits_{k=1}^{4} a_k = \sum \limits_{k=1}^{3} a_k + a_4 = (a_1+a_2+a_3) + a_4
$$


我们能证明$(a_1+a_2+a_3) + a_4$ 与 $(a_1+a_2)+(a_3+a_4)$ 或 $a_1+(a_2+a_3+a_4)$ 相同。因此我们可以再次省略括号并定义 $\sum \limits_{k=1}^4 a_k = a_1+a_2+a_3+a_4$ . 继续用这种方法，我们发现$(a)$和$(b)$两个步骤给出了$\sum \limits_{k=1}^n a_k$ $(I.22)$ 的完整定义。$(I.21)$ 的和式只是$(I.22)$ 一种可选的书写方式. 它可用一般的加法结合律来证明，这里我们不尝试证明。  
读者应该注意到归纳法定义和归纳证明包含相同的思想。归纳法定义也被称为**递归定义**.




## I 4.8 绝对值和三角不等式

不等式的计算在微积分中经常出现，在涉及绝对值的概念时显得特别重要。

如果 $x$ 是一个实数, $x$ 的绝对值是一个非负实数，记为$x$,定义如下：




$$
|x| =
\left\{
\begin{array}{}
x & \mathrm{if} \ x \ge 0 \\
-x & \mathrm{if} \ x \le 0 \\
\end{array}
\right.
$$


注意到$-\lvert x \rvert  \le x \le \lvert x \rvert$. 当在实数轴上表示实数时，$\lvert x \rvert$ 的几何意义是点$x$与原点$0$的距离. 如果$a>0$ 且点$x$在$-a$和$a$之间，则$\lvert x \rvert$比$a$ 更靠近原点. 这一事实的解析描述如下：



**定理 I.38**$\quad$如果$a \ge 0$, 则$\lvert x \rvert \le a$ 当且仅当 $-a \le x \le a$.   

**证明：** 有两个命题要证明：首先，不等式$\lvert x \rvert \le a$ 蕴含着两个不等式$-a \le x \le a$ 同时成立. 反过来，$-a \le x \le a$ 蕴含着 $\lvert x \rvert \le a$.     
假设$\lvert x \rvert \le a$. 则我们也有$-a \le -\lvert x \rvert$ .  由绝对值定义知$-\lvert x \rvert \le x \le \lvert x \rvert$ , 所以$-a \le -\lvert x \rvert \le x \le \lvert x \rvert \le a$ 得证.  
下面证明逆命题. 假设$-a \le x \le a$. 那么根据定义，当$x \ge 0$ 时有$\lvert x \rvert = x \le a$ ; 当$x \le 0$ 时有$\lvert x \rvert = -x \le a$. 所有情况下我们都有$\lvert x \rvert \le a$ 成立，逆命题得证.    
这个定理的几何意义如图：  

![](https://imagebed.deepmind.top/img/calculus1_basics_p4/1.png)

作为定理$I.38$ 的推论，我们很容易推导出一个重要不等式，称为**三角不等式**。它表明两个实数之和的绝对值不超过这两个实数绝对值之和。



**定理I.39 (三角不等式)**$\quad$对任意实数$x$ 和 $y$,  我们有


$$
|x+y| \le |x| + |y|
$$


**证明：** 将不等式$-\lvert x \rvert \le x \le \lvert x \rvert$ 和$-\lvert y \rvert \le y \le \lvert y \rvert$ 相加，我们得到：


$$
-(|x|+|y|) \le x+y \le |x| + |y|
$$


由定理$I.38$ 我们有 $\lvert x+y \rvert \le \bigl| \lvert x \rvert+\lvert y \rvert \bigr| = \lvert x \rvert + \lvert y \rvert$ 得证.      
如果我们取$x = a - c$ ,  $y = c-b$，则$x+y=a-b$ . 三角不等式化为：  


$$
|a-b| \le |a-c| + |b-c|
$$

这种形式的三角不等式经常在实践中使用。  


因为$\lvert y \rvert = \lvert -y \rvert$  代入三角不等式得  $\lvert x - y \rvert \le \lvert x \rvert + \lvert y \rvert$.  从而我们有

$$
|x \pm y| \le |x| + |y|
$$

三角不等式另一个常见的变形是：

$$
|x-y| \ge \bigl| |x|-|y| \bigr|
$$

**证明:** 对$\vert x \vert$ 应用三角不等式：  

$\vert x \vert  =  \vert (x-y)+y \vert  \le  \vert x-y \vert  +  \vert y \vert$  两边同减$\vert y \vert$ 得：

$\vert x \vert - \vert y \vert  \le  \vert x-y \vert$.
对$\vert y \vert$ 应用三角不等式：   

$\vert y \vert  =  \vert (y-x)+x \vert  \le  \vert y-x \vert + \vert x \vert  =  \vert x-y \vert + \vert x \vert$  两边同减$\vert x \vert$ 有：

$\vert y \vert - \vert x \vert  \le  \vert x-y \vert$  两边乘$-1$得 $\vert x \vert - \vert y \vert  \ge - \vert x-y \vert$.

结合得到的两个不等式有：  

$- \vert x-y \vert  \le  \vert x \vert - \vert y \vert  \le  \vert x-y \vert$   根据定理$I.38$有：  

$\bigl\vert \vert x \vert - \vert y \vert  \bigr\vert \le  \vert x-y \vert$ 即 $\vert x-y \vert  \ge \bigl\vert \vert x \vert - \vert y \vert \bigr\vert$ 得证.       


​                        
利用数学归纳法，我们可以把三角不等式推广到以下形式：

**定理I.40** $\quad$对任意实数$a_1, a_2, \cdots a_n$, 我们有：  


$$
\bigg| \sum \limits_{k=1}^n a_k \bigg|  \le \sum \limits_{k=1}^n |a_k|
$$


**证明：** 当$n=1$ 时，不等式显然成立 (trivial).  当$n=2$时，$\lvert a_1+a_2 \rvert \le \lvert a_1 \rvert+\lvert a_2 \rvert$ 就是三角不等式.  假设不等式对于$n$个实数都成立，则对于$n+1$ 个实数，我们有  


$$
\bigg| \sum \limits_{k=1}^{n+1} a_k \bigg|=\bigg|\sum \limits_{k=1}^n a_k + a_{n+1}\bigg| \le \bigg| \sum \limits_{k=1}^n a_k\bigg| + |a_{n+1}| \le \sum \limits_{k=1}^n |a_k| + |a_{n+1}| = \sum \limits_{k=1}^{n+1} |a_k| 
$$




因此如果不等式对$n$ 个实数成立，对$n+1$个实数也成立. 根据数学归纳法，不等式对所有正整数$n$ 都成立.  

下个定理描述了另一个重要不等式，我们在学习向量代数时会用到它。  

**定理 I.41  Cauchy-Schwarz不等式** $\quad$如果$a_1,a_2,\cdots , a_n$ 和$b_1,b_2,\cdots ,b_n$ 是任意实数，我们有


$$
\biggl( \sum \limits_{k=1}^n a_kb_k \biggr)^2 \le \biggl(\sum \limits_{k=1}^n a_k^2 \biggr) \biggl( \sum \limits_{k=1}^n b_k^2 \biggr)
$$


等号成立当且仅当存在实数$x$ 使得 $a_kx+b_k =0$ 对$k=1,2,\cdots, n$ 成立.

**证明：** 对任意正整数$k$ 我们有$(a_kx+b_k)^2 = a_k^2x^2+2a_kb_kx +b_k^2$   两边分别取$k=1,2,\cdots, n$ 求和可得


$$
\begin{align}
\sum \limits_{k=1}^n (a_kx+b_k)^2 &= \sum \limits_{k=1}^n (a_k^2x^2+2a_kb_kx +b_k^2) \\
&= x^2 \sum \limits_{k=1}^n a_k^2 + 2x \sum \limits_{k=1}^n a_kb_k + \sum \limits_{k=1}^n b_k^2
\end{align}
$$


令 $B = \sum \limits_{k=1}^n a_kb_k$,  $A=\sum \limits_{k=1}^n a_k^2$ , $C=\sum \limits_{k=1}^n b_k^2$ , 我们要证$B^2 \le AC$.  

因为平方和是一个非负数，我们有$\sum \limits_{k=1}^n (a_kx+b_k)^2 \ge 0$ 即 $Ax^2+2Bx+C \ge 0$ 且 $A \ge 0$.
当$A=0$ 时 有$a_k=0$ 则$B$ 也为$0$, 此时不等式为$0 \le 0$ 显然成立.     
当$A>0$ 时，不等式左边配方：  


$$
\begin{align}
Ax^2+2Bx+C &= A(x^2+\dfrac{2B}{A}x) + C \\
&= A(x+\dfrac{B}{A})^2-\dfrac{B^2}{A} + C \\
&= A(x+\dfrac{B}{A})^2 + \dfrac{AC-B^2}{A} \ge 0

\end{align}
$$


当$x=-\dfrac{B}{A}$ 时，不等式左边取得最小值，所以$ \dfrac{AC-B^2}{A} \ge 0$ 必然成立，即 $B^2 \le AC$ 得证.   
不难验证，等号成立当且仅当存在实数$x$ 使得 $a_kx+b_k =0$ 对$k=1,2,\cdots, n$ 成立.  $\#$


## 4.10  数学归纳法的杂题

**13. (a)**  令$p$是一个任意正整数，证明

$$
b^p - a^p = (b-a)(b^{p-1}+b^{p-2}a+b^{p-3}a^2+\cdots+ ba^{p-2}+a^{p-1})
$$


(提示：利用和的套缩性(telescoping property))

**(b)** 令$p$和$n$表示正整数，利用(a)的结论证明：




$$
n^p \lt \dfrac{(n+1)^{p+1}-n^{p+1}}{p+1} \lt (n+1)^p
$$




__(__**c**__)__  用数学归纳法证明


$$
\sum_{k=1}^{n-1}k^p \lt  \dfrac{n^{p+1}}{p+1}  \lt \sum_{k=1}^n k^p
$$


(b)部分的结论将有助于作出从$n$到$n+1$ 的归纳步骤.



**(a)证明:**   先把等式右边重写为求和记号的形式，再按照分配律进行计算，直到化简为等式左边


$$
\begin{align}
& (b-a)(b^{p-1}+b^{p-2}a+b^{p-3}a^2+\cdots+ ba^{p-2}+a^{p-1}) \\
&= (b-a) \left( \sum_{k=0}^{p-1} b^{p-1-k}a^k \right) \\
&= b\left( \sum_{k=0}^{p-1} b^{p-1-k}a^k \right)-a\left( \sum_{k=0}^{p-1} b^{p-1-k}a^k \right)\\
&= \sum_{k=0}^{p-1} b^{p-k}a^k -\sum_{k=0}^{p-1} b^{p-1-k}a^{k+1}\\
&= \sum_{k=0}^{p-1} b^{p-k}a^k - \sum_{k=1}^{p} b^{p-k}a^k \\
&= b^p + \sum_{k=1}^{p-1}b^{p-k}a^k -\left(\sum_{k=1}^{p-1}b^{p-k}a^k + a^p \right)\\
&= b^p - a^p
\end{align}
$$



**(b) 证明：** 由二项式定理我们有：



$$
(n+1)^{p+1} = \sum_{k=0}^{p+1} \binom{p+1}{k}n^k
$$


所以

$$
\begin{align}
\dfrac{(n+1)^{p+1}-n^{p+1}}{p+1} &= \dfrac{1}{p+1} \left[\left(\sum_{k=0}^{p+1} \binom{p+1}{k}n^k\right)-n^{p+1}\right] \\
&= \dfrac{1}{p+1}\left[ n^{p+1}+(p+1)n^p + \left(\sum_{k=0}^{p-1} \binom{p+1}{k}n^k \right)- n^{p+1}\right]\\
&= n^p + \dfrac{1}{p+1}\left(\sum_{k=0}^{p-1} \binom{p+1}{k}n^k \right) 
\end{align}
$$


因为$n$和$p$都是正整数，以上等式右边第二项必为正，所以有


$$
\dfrac{(n+1)^{p+1}-n^{p+1}}{p+1} > n^p
$$


即左边不等式得证.

把$b=n+1,\ a=n,\ p=p+1$ 带入(a)的结论有


$$
(n+1)^{p+1}-n^{p+1}=(n+1-n)\cdot((n+1)^{p}+n(n+1)^{p-1}+n^2(n+1)^{p-2}+\cdots + n^{p-1}(n+1)+n^{p})
$$


因此


$$
\begin{align}
& \dfrac{(n+1)^{p+1}-n^{p+1}}{p+1} \\
&= \dfrac{1}{p+1}((n+1)^{p}+n(n+1)^{p-1}+n^2(n+1)^{p-2}+\cdots + n^{p-1}(n+1)+n^{p}) \\
&< \dfrac{1}{p+1}((n+1)^{p}+ (n+1)(n+1)^{p}+{(n+1)}^2(n+1)^{p-2}+\cdots + {(n+1)}^{p-1}(n+1)+{(n+1)}^{p})\\
&= \dfrac{1}{p+1}((n+1)^{p}+p(n+1)^p) \\
&= \dfrac{1}{p+1} (p+1)(n+1)^p \\
&= (n+1)^p
\end{align}
$$




右边不等式得证.   $\#$



**(**__c__**) 证明:**    当$n=1$时，我们有


$$
\sum_{k=1}^{n-1} k^p = \sum_{k=1}^{0}k^p = 0\ ,\quad \dfrac{n^{p+1}}{p+1}=\dfrac{1}{p+1}\ ,\quad \sum_{k=1}^{1} k^p =1
$$


求和式$\sum\limits_{k=a}^b f(k)$ 定义为整数$k$取遍$a\le k \le b$ 时所有项$f(k)$的和. 当$a>b$ 时，则不存在满足条件的$k$，此时定义为空和 (empty sum), 空和的值定义为0. 同理，$\prod\limits_{k=a}^b f(k)$ 在$a<b$时定义为空积 (empty product)，空积的值定义为1.

由于$p$是正整数, 则$0 < \dfrac{1}{p+1} < 1$ 成立，因此不等式在$n=1$这个base case下成立.

令$m$为任意$\ge 1$ 的正整数，假设$n=m$时这对不等式成立.  对于左边不等式我们有：


$$
\begin{align}
\sum_{k=1}^{m-1} k^p \lt \dfrac{m^{p+1}}{p+1} \hspace{-4em} \\
\Longrightarrow \sum_{k=1}^{m} k^p - m^p \lt \dfrac{m^{p+1}}{p+1} \hspace{-6.5em} \\
\Longrightarrow \sum_{k=1}^{m} k^p &\lt \dfrac{m^{p+1}}{p+1} + m^p \\
&\lt \dfrac{m^{p+1}}{p+1} + \dfrac{(m+1)^{p+1}-m^{p+1}}{p+1} \quad(根据(b)的结论) \\
&= \dfrac{(m+1)^{p+1}}{p+1}

\end{align}
$$


这就证明了左边不等式对所有正整数$n \ge 1$ 都成立.

对于右边的不等式有：


$$
\begin{align}
\dfrac{m^{p+1}}{p+1} < \sum_{k=1}^{m} k^p \hspace{-8em} \\
&\Longrightarrow \dfrac{m^{p+1}}{p+1} < \sum_{k=1}^{m+1} k^p - (m+1)^p \\
&\Longrightarrow \dfrac{m^{p+1}}{p+1} + (m+1)^p < \sum_{k=1}^{m+1} k^p \\
&\Longrightarrow  \dfrac{m^{p+1}}{p+1} + \dfrac{(m+1)^{p+1}-m^{p+1}}{p+1}  < \dfrac{m^{p+1}}{p+1} + (m+1)^p < \sum_{k=1}^{m+1} k^p \\
&\Longrightarrow \dfrac{(m+1)^{p+1}}{p+1} <  \sum_{k=1}^{m+1} k^p

\end{align}
$$


这就证明了右边不等式对所有正整数$n \ge 1$ 都成立.    $\#$



