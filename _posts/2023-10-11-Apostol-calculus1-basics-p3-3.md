---
title: Apostol微积分Ⅰ基础篇P3 实数系公理之完备性公理
date: 2023-10-11 00:03:40 +0800
categories: [数学,微积分]
tags: [微积分基础,实数理论]
---

## 3.6 整数和有理数

实数集$R$ 的某些子集具有区别于其他实数的特殊性质。本节讨论整数集和有理数集这两个子集。  
我们从数1开始引入正整数。数1的存在性由域公理4所保证。数 $1+1$ 用 $2$ 表示，数 $2+1$ 用 $3$ 表示，数 $3+1$ 用 $4$ 表示 $\cdots$ 以此类推。通过这种重复加1的方法得到的数$1,2,3 \cdots$ 全都是正的，称为正整数。严格来说，正整数的这种描述并不完整，因为没有详细解释“以此类推”“重复加1”指的是什么。虽然这些表述的直观意义似乎是清楚的，但为了实数系统的严谨性，必须给正整数更准确的定义。定义正整数的方法有很多种，其中一个方便的方法是引入归纳集 (inductive set) 的概念。   
**归纳集的定义** 一个实数的集合如果具有以下两个性质，就被称为归纳集.       
$(a)$ 数 $1$ 在集合中    
$(b)$ 对集合中的任意一个数$x$, 数 $x+1$ 也在集合中.  
例如，$R$ 是一个归纳集，$R^+$ 也是一个归纳集。现在我们把正整数定义为属于每个归纳集的那些实数。   
**正整数的定义** 如果一个实数属于每一个归纳集，则这个实数叫做正整数.      
令$P$ 表示所有正整数的集合。 那么 $P$ 本身是一个归纳集。因为$(a)$ 它包含了$1$. $(b)$ 如果它包含了$x$，则它包含了$x+1$. 因为 $P$ 的元素属于每个归纳集，所以把 $P$ 称为**最小归纳集**。 集合$P$ 的这个性质，为归纳证法这一类推理提供了逻辑基础。第四节将给出关于归纳证法的详细讨论。   
正整数的负值称为负整数。正整数和负整数以及0一起构成一个集合 $Z$, 称为**整数集**。  
若是实数系统的详尽论述，到了这个阶段有必要证明关于整数的某些定理。例如，两个整数的和，差或积是一个整数，但两个整数的商不一定是整数。然而我们不在这里详述这些证明。     
整数的商$\dfrac{a}{b}$ 称为**有理数**，用 $Q$ 表示。有理数集$Q$包含了整数集$Z$作为一个子集。有理数集$Q$满足所有域公理和序公理，是一个有序域。不在$Q$中的实数称为**无理数**。   

## 3.7 实数作为直线上的点的几何解释

1902年，希尔伯特《几何基础》发表，5组数学公理确立了**欧几里德直线上的点与实数**的**一一对应**关系，是数学发展史上的里程碑事件。直线通常叫做实线或实轴。而且习惯上可互换使用实数和点这两个词。于是我们经常讲点$x$而不说对应于实数$x$的点。如图，我们选择直线上一点表示$0$，在 $0$ 右边的某一点表示 $1$。这个选择确定了尺度。  
实数中的序关系有一个简单的几何解释。如图。如果$x<y$，则点$x$位于点$y$的左边。正数位于$0$的右边而负数位于$0$的左边。如果$a<b$，当且仅当点$x$位于$a$和$b$之间时$x$满足不等式$a<x<b$.           

![](https://cdn.jsdelivr.net/gh/dlcai/image-bed/img/calculus1_basics_p3/7.png)  





## 3.8 集合的上界，最大元，最小上界 (上确界)   

前面列出的9条公理包含了初等代数中通常论述的实数的性质。在微积分中，还有一个在初等代数中不讨论的重要公理，这个公理 (或与之等价的性质) 被用来证明无理数的存在。   
在初等代数中，当我们尝试解某些二次方程时就会出现无理数。例如求一个实数满足$x^2=2$.  由前9条公理我们不能证明 $R$ 中存在这样一个$x$. 因为$Q$ 也满足所有域公理和序公理，但不存在平方为$2$的有理数。 公理10使我们能在实数系中引进无理数，并给出了实数系的连续性。这个性质是微积分学的逻辑结构的基石。    
为了方便叙述公理10，我们先引入一些专有名词和记号。    

**有序集的概念** 某个集合上定义了一种序，便是一个有序集。例如，如果对任意两个有理数$a$和$b$, 规定 $a<b$ 即 $b-a$ 是正有理数，则有理数集 $Q$ 是一个有序集。   
**上界的概念** 上界是一个与有序集有关的特殊元素，指的是有序集中大于或等于它的子集中一切元素的元素。设$U$是一个有序集，若存在$y \in U$, 对任意$x \in S \subseteq U$ 都有 $x \le y$ . 则称 $y$ 是子集$S$ 的一个上界。   

**上界在实数集R上的定义** 假定$S$是一个非空实数集，并假定对$S$中的每个$x$, 存在一个数$B$, 使得    

$$
\begin{align}
x \le B
\end{align}
$$

那么就说$x$是以 $B$ 为**上界**的 ($S$ is bounded above by $B$) 。数 $B$ 称为 $S$ 的一个上界。 我们说$B$ 是一个上界，因为每个大于$B$ 的数也都是上界。如果上界 $B$ 也是$S$ 中的数，则称$B$ 为$S$ 的**最大元**. 至多可能存在一个这样的$B$. 如果存在，记作$B = max\ S$.     
于是，如果$B \in S$ 且 $x \le B$，$\forall x \in S$, 则 $B= max \ S$ .    
一个没有上界的集合称为是**无上界**的 (unbounded above).     
以下例子用来说明这些术语的意义.  
**例1** 令 $S$ 是所有正实数的集合，这个集合是无上界的。它没有上界也没有最大元。    
**例2** 令 $S$ 是所有满足 $0\le x \le 1$ 的实数 $x$ 的集合。这个集合以 $1$ 为上界。$1$ 也是最大元。    
**例3** 令 $T$ 是所有满足 $0\le x \lt 1$ 的实数 $x$ 的集合。这个集合以1为上界，但没有最大元。     
某些集合 (如例3中的集合) 有上界, 但没有最大元。对这些集合，有一个取代最大元的概念，这个概念称为**最小上界**，其定义如下：    
**最小上界的定义** 如果数$B$ 具有以下两个性质，则称$B$是非空集合$S$ 的最小上界.     
$(a)$ $B$ 是$S$ 的一个上界.   
$(b)$ 小于$B$ 的数不是 $S$ 的上界.    
如果$S$有最大元，这个最大元也是最小上界。但如果$S$没有最大元，它仍然可以有一个最小上界。在例3中，$T$虽然没有最大元，但数$1$是 $T$ 的最小上界。     



![](https://jsd.onmicrosoft.cn/gh/dlcai/image-bed/img/calculus1_basics_p3/8.png)





**最小上界的唯一性**  两个不同的数不可能是同一集合的最小上界.    
**证明:**  假设$B$和$C$都是集合$S$的最小上界，因为$B$是最小上界，由性质$(b)$有$C\ge B$. 类似地，因为$C$是最小上界, 有$B \ge C$. 所以$B=C$. 即最小上界是唯一的. $\#$    
这个定理告诉我们，一个集合如果有最小上界，那么这个最小上界是唯一的。因为我们可以只说“最小上界”，而不必说”一个最小上界”。     
通常用更简明的术语**上确界**来指一个集合的最小上界，缩写为$\sup$.  用$B = \sup S$ 表示$B$ 是$S$的最小上界/上确界.      

## 3.9 最小上界公理 (完备性公理)

现在我们来叙述实数系的最小上界公理。    
**公理10**&nbsp;&nbsp; 非空有上界的实数集$S$必有上确界. 即存在一个实数$B$ 使得$B = \sup S$.      
再次强调，$S$的上确界不必是$S$的一个元素，事实上，当且仅当$S$存在最大元时$\sup S \in S$.  这种情况下$\max S = \sup S$.    
类似地，我们可以给出下界，有下界，最小元的定义，这里不一一写出。最小元记作 $\min S$.     
一个数$L$如果满足$(a)$ $L$ 是$S$的一个下界  $(b)$ 大于$L$的数不是$S$的下界. 则数$L$叫做$S$的 **最大下界 (下确界)**. 下确界存在时也是唯一确定的，记作 $\inf S$. 如果$S$存在最小元，则 $\min S = \inf S$.          
利用公理10可以证明以下定理：  
**下确界定理**  非空有下界的实数集$S$必有下确界.  即存在一个实数$L$ 使得$L=\inf S$.     
**证明：** 令$-S$ 表示$S$ 中数的负值的集合.  则$-S$非空且有上界. 由公理10存在一个实数$B$, 这个$B$ 是$-S$ 的上确界. $S$中每个元素$x$取负值后对应$-S$ 中的$-x$. 由上确界性质$(a)$ $B$ 是一个上界，则对$\forall x \in S$ 有 $-x \le B$ 即$x \ge -B$. 所以$-B$是$S$的一个下界. 由上确界性质$(b)$ 小于$B$ 的数都不是$-S$ 的上界，对任意$B'<B$, 存在$-x \in -S$, 使得$-x>B'$. 即对任意$-B'>-B$, 都存在$x \in S$, 使得$x<-B'$. 所以$-B$ 是$S$的最大下界. 即$-B=\inf S$.    $\#$   
      
再看前面的例子，例1中所有正实数的集合，数$0$是集合的下确界，这个集合没有最小元. 例2和例3中数$0$是最小元.    
这些例子都容易确定集合$S$是否有上界或下界，也容易确定上确界$\sup S$ 和下确界$\inf S$. 下面的例子说明确定上界或下界是否存在有时是困难的.   
**例4**  令 $S$ 是形为$(1+1/n)^n$ 的所有数的集合，其中$n=1,2,3,\cdots$ . 例如，取$n=1,2$和$3$我们得到$S$中的数$2,\dfrac{9}{4}$和$\dfrac{64}{27}$.集合中的每个数都大于1，因此集合是有下界的.    

$$
\begin{align}
\hspace{-2em}\dfrac{(1+\dfrac{1}{n+1})^{n+1}}{(1+\dfrac{1}{n})^n} &= \dfrac{(1+\dfrac{1}{n+1})^{n+1}}{(1+\dfrac{1}{n})^{n}\cdot (1+\dfrac{1}{n})} \cdot (1+\dfrac{1}{n}) \\
&= (1+\dfrac{1}{n}) \left(\frac{1+\frac{1}{n+1}}{1+\frac{1}{n}}\right)^{n+1} \\
&= (1+\dfrac{1}{n})\left(\frac{\frac{n+2}{n+1}}{\frac{n+1}{n}}\right)^{n+1} \\
&= (1+\dfrac{1}{n})\left(\dfrac{n^2+2n}{(n+1)^2}\right)^{n+1} \\
&= (1+\dfrac{1}{n})\left(1-\dfrac{1}{(n+1)^2}\right)^{n+1} \\
&\ge (1+\frac{1}{n})(1+(n+1)\left(-\frac{1}{(n+1)^2}\right))  (伯努利不等式(1+x)^n\ge 1+nx) \\
&= (1+\frac{1}{n})(1-\dfrac{1}{n+1}) \\
&= \dfrac{n+1}{n} \cdot \dfrac{n}{n+1} = 1
\end{align}
$$



所以数列$(1+1/n)^n$ 是单调递增的，$n=1$时取得最小值$2$. 所以集合$S$的下确界$\sup S = \min S = 2$.        
下面来证明集合$S$ 有上界，只须证单调递增数列$(1+1/n)^n$ 有上界.     
$$
\begin{align}
(1+\dfrac{1}{n})^n &= \sum_{k=0}^n C_n^k(\dfrac{1}{n})^k  \quad (二项式定理) \\
&= \sum_{k=0}^n \dfrac{n!}{k!(n-k)!} (\dfrac{1}{n})^k \\
&= 1+1+\sum_{k=2}^n\dfrac{n(n-1)\cdots (n-(k-1))}{k!}\dfrac{1}{n^k} \\
&= 1+1+\sum_{k=2}^n\dfrac{1(1-\frac{1}{n})\cdots (1-\frac{k-1}{n})}{k!} \\
&\lt 2+\sum_{k=2}^n\dfrac{1}{k!} \\
&= 2+(\dfrac{1}{2!}+\dfrac{1}{3!}+\cdots +\dfrac{1}{n!}) \\
&\lt 2+(\dfrac{1}{2 \times 1}+\dfrac{1}{3 \times 2}+\cdots +\dfrac{1}{n\times (n-1)}) \quad (放缩)\\
&= 2+(\dfrac{1}{1}-\dfrac{1}{2})+(\dfrac{1}{2}-\dfrac{1}{3})+\cdots ++(\dfrac{1}{n-1}-\dfrac{1}{n}) \quad(裂项求和)\\
&= 2+(1-\dfrac{1}{n}) \lt 3 \quad \#
\end{align}
$$


所以集合$S$有上界. 公理10告诉我们$S$必有上确界。这种情况下不容易通过$S$的表达式来确定上确界$\sup S$的值。后面有一章我们将了解到$\sup S$是一个近似等于$2.718$的无理数。这是微积分中一个重要的数，称为欧拉数$e$.    

## 3.10 实数系的阿基米德性质

本节包含了实数系的若干重要性质，这些性质是最小上界公理的结果。     
**定理I.28** &nbsp;&nbsp;正整数$1,2,3,\cdots $ 的集合$P$ 是没有上界的.      
**证明：** 假设集合$P$ 有上界. 因为$P$是非空的，由公理10知$P$必有最小上界 (整数集也有最小上界性，有理数集则没有)，设$P$ 的最小上界是$b$, 则由最小上界的定义，$b-1$ 不是$P$ 的上界，即存在正整数$n$, 使得$n>b-1$. 对这个$n$，我们有$n+1 > b$.  由正整数的最小归纳集定义，$n+1$ 也在$P$ 中，这与$b$ 是$P$ 的上界矛盾，所以$P$ 是没有上界的. $\#$     
作为定理I.28的推论，我们有以下结论：   
**定理I.29**  对任意实数$x$, 存在正整数$n$，使得$n>x$.       
**证明：** 原命题的否定表述为：存在某个实数$x$，对任意的正整数都有$n <= x$.   即正整数集$P$ 存在一个上界$x$，这与定理I.28矛盾，故原命题的否定为假，则原命题得证。      
**定理I.30 (阿基米德性质)**  如果$x>0$ 且 $y$ 是任意实数，则存在正整数$n$, 使得$nx>y$.       
**证明：** 把定理I.29中的$x$ 替换为 $y/x$ 即得证.    
阿基米德性质的几何意义是：一条线段无论有多长，都可以用给定任意短的线段的有限倍数来覆盖。换句话说，一根小直尺只要使用足够多次就能度量任意大的距离。当年阿基米德意识到这是直线的一个基本性质并把它明确地列为几何公理之一。在19至20世纪创立的非阿基米德几何中这条公理被去掉了。   
由阿基米德性质，我们能证明以下定理。这个定理在积分学的讨论中非常有用。   
**定理I.31** 如果对每个整数$n \ge 1$,  实数$a, x, y$ 满足不等式    
$$
\begin{align}
a \le x \le a + \dfrac{y}{n}
\end{align}
$$
则 $x = a$.    

**证明：** 如果$x>a$, 则有$x-a >0$.  由阿基米德性质，存在正整数$n$, 使得$n(x-a)>y$ 即$x> a+\dfrac{y}{n}$ ，这与不等式$x \le a+\dfrac{y}{n}$ 矛盾，因此不能有$x>a$, 于是必须有$x=a$.          

## 3.11 上确界和下确界的基本性质

这节讨论上确界和下确界的三个基本性质，这些性质在微积分中将会用到。第一个性质指出，任何有上确界的实数集包含任意接近它的上确界的点。类似地，任何有下确界的实数集包含任意接近它的下确界的点。   