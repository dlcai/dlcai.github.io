---
title: Basic Analysis C0 集合论语言回顾
date: 2024-09-20 08:32:45 +0800
categories: [数学, 数学分析]
tags: [集合论基础,良序原理,数学归纳法,等价类,基数]
---

## 集合 Sets

> **子集的定义 (subsets)**  
> $(i)$ 如果$x \in A \implies x \in B$ 我们说A是$B$ 的子集，记为 $A \subseteq B$. 也就是说，$A$的所有成员也都是$B$ 的成员. 同样的包含关系也可以记为 $B \supseteq A$.    
> $(ii)$ 集合相等的定义：如果$A \subseteq B$ 且 $B \subseteq A$ ，我们说集合A与集合$B$ 相等，记为$A=B$. 也就是说，$A$和$B$包含的元素完全相同. 集合$A$和集合$B$ 不相等则记为$A \neq B$.     
> $(iii)$ 如果$A \subseteq B$ 且 $A \neq B$ ，我们说$A$是$B$的真子集 (proper subset)，记为 $A \subset B$.     

> **集合运算的定义 (set operations)**   
> $(i)$ 两个集合$A$ 与$B$ 的并集 (union) 定义为：   
> $A \cup B := \Bigl\lbrace{ x \mid x \in A \ 或 \  x \in B \Bigr\rbrace}$   
> $(ii)$ 两个集合$A$ 与$B$ 的交集 (intersection) 定义为：  
> $A \cap B := \Bigl\lbrace x \mid x \in A \ 且 x \in B\Bigr\rbrace$    
> $(iii)$ $B$ 在$A$ 中的相对补集 (the complement of B relative to A, 或记为集合论差$A-B$ ) 定义为：  
> $A \setminus B := \Bigl\lbrace x \mid x \in A \ 且\ x \notin B\Bigr\rbrace$   
> ($iv$) 更常见的是绝对补集，如果$A$ 为全集 (universe) 或从上下文可知$A$包含$B$，  
> 我们说$B$ 的补集 (complement of $B$), 记为$B^{\complement}$ 而不是 $A \setminus B$ . 	    
> $(v)$ 如果$A \cap B = \emptyset$ , 我们说$A$和$B$ 是分离的 (disjoint).   

> **德摩根律 (Demorgan)**  如果$A$ , $B$,  $C$ 为任意三个集合，我们有  
> $1)$  $(B \cup C)^{\complement} = B^{\complement} \cap C^{\complement}$       
> $2)$  $(B \cap C)^{\complement} = B^{\complement} \cup C^{\complement} $   
> 更一般地，  
> $3)$ $A - (B \cup C) = (A - B) \cap (A-C)$   
> $4)$ $A - (B \cap C) = (A-B) \cup (A-C)$     

**证明：** 只要证明 $3)$ 和 $4)$ 再把$A$ 替换为全集就能证明$1)$和 $2)$ .    
我们来证明$A-(B \cup C) = (A-B) \cap (A-C)$ . 其余等式的证明作为练习.    
根据集合相等的定义需证明： $A-(B\cup C) \subseteq (A-B)\cap(A-C)$ 且 $(A-B)\cap(A-C)\subseteq A-(B\cup C)$.  
根据子集的定义就是要证：  
$x \in A-(B\cup C)\implies x \in (A-B)\cap (A-C)$  且 $x \in (A-B)\cap(A-C)\implies x\in A-(B\cup C)$.   
假设$x \in A-(B\cup C)$.  由相对补集定义有 $x \in A$ 且 $x \notin B\cup C$.   
由并集的定义有：$x \in A$ 且 $x \notin B$ 且 $x \notin C$  即 $x \in (A-B)$ 且 $x \in(A-C)$   
由交集的定义有 $x \in (A-B)\cap(A-C)$ 
所以 $A-(B\cup C) \subseteq (A-B)\cap(A-C)$  得证.  
假设$x \in (A-B)\cap(A-C)$.    
$x \in (A-B) \implies x \in A$ 且 $x \notin B$ ,  $x \in (A-C) $ $\implies x \in A$ 且 $x \notin C$ .   
$\therefore$ $x \notin B$ 且 $x \notin C$  $\implies x \notin B \cup C$       
$\therefore$ $x \in A$ 且 $x \notin (B \cup C)$     
由相对补集定义即$x \in A - (B\cup C)$ ,     
$(A-B)\cap(A-C) \subseteq A - (B\cup C)$  得证.   $\square$       

有时我们也需要同时对多个集合进行交集或并集操作。如果集合的数量只是有限多个，那么我们可以只需多次进行交集或并集运算。然而，假设我们有一个无限的集族 (collection of sets, 集合的集合) $\lbrace{ A_1,A_2,A_3\cdots \rbrace}$ .  我们定义：  


$$
\begin{align}
\bigcup_{n=1}^{\infty} A_n &= \lbrace\ x \mid 至少存在一个n \in \mathbb{N},使得x \in A_n \ \rbrace \\
\bigcap_{n=1}^{\infty} A_n &= \lbrace\ x \mid 对每个n\in \mathbb{N} \ 都有x \in A_n\rbrace
\end{align}
$$



根据集族的并集和交集的定义，任意多个集合之间的交或并运算都自动满足结合律。即写作$A_1 \cap A_2\cap\cdots A_n$ 可以不用加括号, 不会产生歧义。

我们也可以用两个自然数来给集族中的集合编号。例如集族 $\lbrace A_{1,1},A_{1,2},A_{2,1},A_{1,3},A_{2,2},A_{3,1},\cdots\rbrace$  可以记为


$$
\bigcup_{n=1}^{\infty}\bigcup_{m=1}^{\infty}A_{n,m} = \bigcup_{n=1}^{\infty}\left(\bigcup_{m=1}^{\infty}A_{n,m}\right)
$$


交运算的记法也类似。不难看出，这两次并运算的结果与执行的次序无关。但是并和交的混合运算交换次序后结果不一定相同，是否可以交换要先进行证明。例如


$$
\bigcup_{n=1}^{\infty}\bigcap_{m=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace
$$


无论给定的$n$多大，因为$m$ 没有上界，总会出现 $k < \dfrac{n}{m} < 1$ 的情况，即集族中必有空集，根据定义，  
空集与任何集合的交集都为空集，则有 $\bigcap\limits_{m=1}^{\infty}\lbrace{ k\in\mathbb{N} \mid mk < n \rbrace} = \emptyset $ .   
所以 $\bigcup\limits_{n=1}^{\infty}\bigcap\limits_{m=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace = \bigcup\limits_{n=1}^{\infty}\emptyset = \emptyset $.          
交换运算顺序原式变为：


$$
\bigcap_{m=1}^{\infty}\bigcup_{n=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace
$$



给定$m$时，因为$n$没有上界， $k < \dfrac{n}{m}$ 可以取遍所有自然数，则有$\bigcup\limits_{n=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace = \mathbb{N}$.       
所以 $\bigcap\limits_{m=1}^{\infty}\bigcup\limits_{n=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace = \bigcap\limits_{m=1}^{\infty} \mathbb{N} = \mathbb{N}$.  交换次序后运算结果并不相等。      



## 数学归纳法 Induction

证明包含正整数(自然数)的命题，一个常见的方法是数学归纳法。  
按照自然方式排序 ($1<2<3<4<\cdots$) 的自然数集 (正整数集) 具有所谓“良序”的性质。  
正整数集$S \subset N$ 存在一个最小元，意味着存在正整数$x \in S$ , 使得对每个$y \in S$ 都有 $x \le y$ .

### 良序原理 (well ordering principle)  

良序原理：每个非空正整数集都有最小元.    
本书把良序原理作为公理，数学归纳法作为定理，这与Apostol Calculus的处理是相反的。

### 数学归纳法 (Induction)

**定理 (数学归纳法原理)**  设$P(n)$是一个关于正整数$n$的命题，如果    
设$P(n)$是一个关于正整数$n$的命题，如果    
$(i)$ (base case)  $n=1$ 时， P(1)成立.  
$(ii)$ (induction step)   如果$P(n)$成立，则$P(n+1)$也成立   
那么$P(n)$ 对所有正整数都成立。   

**证明：** 令 $S = \lbrace{ n \in \mathbb{N} \mid P(n)不成立 \rbrace}$ , 即$S$为使得$P(n)$不成立的所有正整数的集合. 要证的结论是$S=\emptyset$ . 我们采用反证法，假设集合$S$ 非空。根据良序原理，此时正整数集$S$存在最小元，记$m \in S$ 为$S$ 的最小元. 由$(i)$ 知 $1 \notin S$, 所以最小元$m > 1$ , 则$m-1$也是正整数. 因为$m$是最小元，所以 $m-1 \notin S$ , 即$P(m-1)$ 成立. 但根据归纳步骤，$P(m-1+1) = P(m)$ 也成立, 这与$m \in S$ ( 即 $P(m)$ 不成立 ) 是矛盾的，故假设不成立, $S = \emptyset$ 得证，即$(i)$ 和 $(ii)$都满足时，$P(n)$ 对所有正整数都成立.   $\square$

有时不把1作为base case更方便，只需改变初始值的记号即可。归纳步骤“$P(n)$ 成立 $ \implies P(n+1) $” 中的“$P(n)$ 成立” 的假设称为归纳假设.    

**例1**  证明：$2^{n-1} \le n!$ 对所有$n \in \mathbb{N}$ 都成立.  
**Proof.**  把命题“$2^{n-1} \le n!$” 记为$P(n)$.   
$(i)$  $n=1$ 时，$2^{1-1}=1!$ , $P(1)$ 显然成立.  
$(ii)$ 假设$P(n)$ 为真，即$2^{n-1}\le n!$ 成立.   
不等式两边同乘$2$有 $2^n \le 2(n!)$    
因为$2 \le n+1$ 对所有$n \in \mathbb{N}$ 都成立，我们有   
$2(n!)\le (n+1)n! = (n+1)!$   则   
$2^n \le (n+1)!$ 成立.  故$P(n+1)$ 成立.  
根据数学归纳法 ，$P(n)$对所有$n \in \mathbb{N}$ 都成立,   
即$2^{n-1} \le n!$ 对所有$n \in \mathbb{N}$ 都成立. $\ \square$    

**例2** 证明：对任意实数$c \ne 1$ 有       
$$
\begin{align}
1 + c + c^2 + \cdots + c^n = \dfrac{1 - c^{n+1}}{1-c}  \quad (等比数列求和公式)
\end{align}
$$


**Proof.** 把要证的命题记为$P(n)$.     
$(i)$  $n = 1$ 时，等式左边 = $1 + c$ ，等式右边$\dfrac{1-c^2}{1-c} = \dfrac{(1+c)(1-c)}{1-c}=1+c$ . $P(1)$成立.    
$(ii)$ 假设$P(n)$成立，则  
    
$$
\begin{align}
1+c+c^2+\cdots+c^n + c^{n+1} &= (1+c+c^2+\cdots+c^n ) + c^{n+1} \\
&= \dfrac{1-c^{n+1}}{1-c} + c^{n+1}  \\
&= \dfrac{1-c^{n+1}+(1-c)c^{n+1}}{1-c} \\
&= \dfrac{1-c^{n+1}+c^{n+1}- c\cdot c^{n+1}}{1-c} \\
&= \dfrac{1- c^{(n+1)+1}}{1-c}
\end{align}
$$


故$P(n+1)$ 也成立. 由归纳法原理，  
等式$1+c+c^2+\cdots+c^n = \dfrac{1-c^{n+1}}{1-c}\ (c\ne1)$ 对所有$n \in \mathbb{N}$ 都成立. $\square$     

**例3**  证明：如果$c \ge -1$ ,  则  


$$
(1+c)^n \ge 1 + nc \quad (\text{Bernoulli's Inequality})
$$


对所有$n \in \mathbb{N}$ 都成立.

**Proof.**  把要证的命题记为$P(n)$.   
$(i)$ $n=1$时，$(1+c)^1 = 1 + 1\cdot c$ , $P(1)$显然成立.  
$(ii)$ 假设$(1+c)^n \ge 1+nc$ 成立，则 

 

$$
\begin{align}
(1+c)^{n+1} &= (1+c)(1+c)^n \\
					  &\ge (1+c)(1+nc) \\
					  &= 1 + nc + c + nc^2 \\
					  &= 1 + (n+1)c + nc^2
\end{align}
$$


因为$nc^2 \ge 0$，$(1+c)^{n+1} \ge 1+(n+1)c$ 成立，即$P(n+1)$也成立 .     
由归纳法原理，如果$c\ge -1$, $(1+c)^n \ge 1+nc$ 对所有$n \in \mathbb{N}$ 都成立.   $\square$     

在归纳步骤，有时假设$P(k)$ 对所有$k=1,2,\cdots n$ 都成立 (而不仅是$k=n$ 时成立)，更容易证明一些命题。 这个原理叫做强归纳法，它与第一数学归纳法是等价的。  


### 强归纳法 (strong induction)

设$P(n)$是一个关于正整数$n$的命题，如果    
$(i)$ (base case)  $n=1$ 时， P(1)成立.  
$(ii)$ (induction step)   $\forall n \ge 1$ ,  $P(k)$ 对$1 \le k \le n$ 的所有整数都成立，可推出$P(n+1)$ 成立.  
则$P(n)$ 对所有正整数都成立。      

在初等数论中，算术基本定理的证明是强归纳法一个经典应用。

**算术基本定理 (唯一因数分解定理)**  任意大于1的整数都可唯一分解成素数的乘积。      

**Fundamental theorem of arithmetic (unique factorization theorem)**  
 Every integer greater than 1 can be represented uniquely as a product of prime numbers, up to the order of the factors. (up to X means X is ignored, 不考虑因数顺序的情况下，分解方式是唯一的).   
唯一性的含义是：如果两种分解方式是相同的，则质因数的个数相同，且各个质因数是一一对应的。这个定理也是1不被当作素数的主要原因：如果1是素数，那它的分解方式不是唯一的，因数的个数可以任意多个，例如 $2 = 2 \cdot 1 = 2 \cdot (1 \cdot 1) = 2 \cdot (1\cdot 1\cdot 1) = \cdots$      

**证明：** 先用强归纳法证明分解的存在性。即任意大于1的整数$n$都能表示成素数的乘积。  
$(i)$ $n = 2 $ 时，2本身就是素数，显然成立。  
$(ii)$ 假设$\forall n >= 2$ , $2 \le k \le n$ 的所有整数$k$都能分解成素数之积，   
如果$n+1$是素数，则整数$n+1$能分解成素数显然成立；  
如果$n+1$ 不是素数，则有$n+1 = n_1 \cdot n_2$ , 其中$2 \le n_1, n_2 \le n$ .   
由归纳假设， $n_1$和$n_2$都能分解成素数之积，则$n+1$能分解成素数之积也成立.     
根据强归纳法，对任意大于1的整数$n$分解的存在性都成立.  
再用第一归纳法证明分解的唯一性。    
记$n = p_1p_2\cdots p_t$ 为整数$n$ 的一种分解方式.  
对素因素的个数$t$进行归纳：  
$(i)$ $t = 1$时，$n$ 仅有一个素因数，即$n=p$的形式，分解的唯一性显然成立.    
$(ii)$ 假设素因数个数为 $t$ 时分解的唯一性成立.   
当素因数个数为 $t+1$ 时，假设存在两种分解方式: $p_1p_2\cdots p_tp_{t+1} = q_1q_2\cdots q_sq_{s+1}$  
则有$p_{t+1} \mid q_1q_2\cdots q_sq_{s+1}$   即 $p_{t+1}$能整除 ( is a divisor of ) $q_1q_2\cdots q_sq_{s+1}$    
$\because$ $p_{t+1}$是素数 且等式右边是素数的乘积，  
$\therefore p_{t+1}$ 必然等于右边某一个素因数，不妨记为$q_{s+1}$ .   
两边分别消去$p_{t+1}$和$q_{s+1}$ 有 $p_1p_2\cdots p_t = q_1q_2\cdots q_s$ .    
根据归纳假设，素因数个数为$t$的整数$p_1p_2\cdots p_t$ 分解方式是唯一的，即  
$t = s$ 且等式两边的素因数是一一对应的.  
所以$p_1p_2\cdots p_tp_{t+1}$ 和 $q_1q_2\cdots q_sq_{s+1}$ 这两种分解方式中的素因数都是一一对应的，  
即不存在两种分解方式，这与假设矛盾，所以当素因数个数为$t+1$时分解的唯一性也成立，  
归纳步骤的结论得证。根据数学归纳法，分解的唯一性得证.     $\square$           

## 函数 Functions

Question: 什么情况下两个集合$A$和$B$的大小相同？   
Answer:  如果两个集合中的元素可以一一配对，则两集合的的大小相同。(Theory of Cardinality By Cantor)      
举个例子来理解：假设你是一个对数字完全没有概念的原始人，你有一群猪和一群羊，但还没学会数数，如何判断猪和羊的数量是否相等呢？把猪全部赶进一个圈子(集合A)，再把羊全刚进另一个圈子(集合B)，然后把猪和羊逐个出来排队，两队并列进行一一配对，如果每头猪刚好能配一只羊，我们就说猪和羊的数量是相等的。(两集合的基数相等)    

为了准确地描述这种“一一对应”关系，我们需要先定义函数/映射。   

 

### 基于集合论的非正式定义  

从集合$A$到集合$B$的函数$f$是一个映射，它为 $\forall x \in A$ 分配一个唯一的$y \in B$ . 记为$f:A \to B$ .    
举个例子，从$S := \{0,1,2\}$ 到 $T := \{0,2\}$ 的函数$f:S\to T$ 可以通过$f(0):=2$, $f(1):=2$ 和$f(2):=0$ 的赋值操作来定义。也就是说，函数$f:A\to B$ 可被看成一个黑盒，我们输入一个$A$中的元素就会输出一个$B$ 中的元素。函数 $f$ 有时也被叫做映射 (a mapping or map)，我们说$f$把$A$映射到$B$.  

函数经常通过某个公式来定义，然而你应该仅把函数看作一个非常大的值表 (指将变量的取值和函数值对应起来的表格). 原因在于同一个函数可以有多种不同的公式表示，而且绝大多数函数是写不出表达式的，只能用表格或曲线图形来表示。    

注意：我们讨论的函数(映射)只考虑一对一或多对一关系，即一个$A$中的元素不可以与多个$B$ 中的元素对应。一对多关系可以用“多值函数”表示，通常我们规定一对多不是映射，因为任何一对多关系的映射都可以直接转化为一对一的关系，只需把这多个元素塞进一个新集合里，这个集合里的元素就是从该输入可能得到的所有输出。  

### 严格的函数定义：笛卡尔积的子集

**笛卡尔积(*Cartesian product*)的定义**  设$A$、$B$ 为集合. 笛卡尔积是定义为

$$
A \times B := \lbrace (x,y) \mid x \in A, y \in B\rbrace
$$

的二元组的集合 (set of tuples).   例如 $\lbrace a,b\rbrace\times \lbrace c,d \rbrace= \lbrace (a,c),(a,d),(b,c),(b,d)\rbrace$ .一个更复杂的例子是集合$[0,1]\times [0,1]$，这是平面的一个子集：被顶点为$(0,0),(0,1),(1,0),(1,0)$ 的正方形所围成。当$A$和$B$是相同的集合，我们常用上标$2$来表示这样的乘积。例如 $[0,1]^2 = [0,1]\times[0,1]$ 或 $\mathbb{R}^2 = \mathbb{R}\times\mathbb{R}$ (笛卡尔直角坐标平面)

**函数的严格定义** 函数$f: A\to B$ 是$A\times B$ 的一个子集，集合$f$中的有序对 $(x,y)\in f$满足:   
对每个$x \in A$ , 都存在唯一的$y\in B$ 与之对应，记为$f(x)=y$ .     
(不能出现两个有序对具有相同的第一个元  $(x,y_1) \in f\ \wedge (x,y_2) \in f \implies y_1=y_2$ )。  
有时把这个有序对的集合$f$ 称为函数的图像 (**graph**) 而不是函数本身。  
集合$A$称为函数$f$的定义域(**domain**) ,有时记为$D(f)$.  集合   
$R(f) := \lbrace{ y \in B \mid \exists\ x \in A\  s.t. f(x)=y \rbrace}$ $= \lbrace f(x)\in B \mid x \in A \rbrace$ 称为函数$f$的值域(**range**).    
集合$B$称为函数$f$的陪域. 值域$R(f)$ （这里指定义域在$f$下的像$f(A)$ ）可能是陪域$B$的真子集 (与$B$不相等). 而定义域总是指$A$. 我们通常假设$f$ 的定义域不为空。

### 像与逆像

**像(image)的定义** 考虑函数$f:A\to B$ ，定义域的子集$C \subseteq A$的像 (**image**或**direct image**) 定义为   

$$
f(C)=\lbrace f(x) \in B \mid x \in C\rbrace
$$


陪域$B$的子集$D\subseteq B$ 的**逆像** (**inverse image**, 也叫原像)定义为 


$$
f^{-1}(D) = \lbrace x \in A \mid f(x) \in D\rbrace
$$


 特别地，有$R(f)=f(A)$  ，即这里函数的值域就是指定义域$A$的像(**image**) 。  

![](https://imagebed.deepmind.top/img/BA-C0/1.png)





**像与逆像举例**   定义函数$f:A\to B$ 为$f(x) := \sin (\pi x)$ . 则有  
则有$f([0,\frac{1}{2}])=[0,1]$ ，$f^{-1}(\{0\})=\mathbb{Z}$   等等.



**与逆像有关的命题** 考虑函数$f:A\to B$ . 令$C$ 和 $D$为$B$ 的子集,  则


$$
\begin{align}
(1)& \quad f^{-1}(C\cup D) = f^{-1}(C) \cup f^{-1}(D) \\
(2)& \quad f^{-1}(C\cap D) = f^{-1}(C) \cap f^{-1}(D) \\
(3)& \quad f^{-1}(C^{\complement}) = (f^{-1}(C))^{\complement}
\end{align}
$$



命题$(3)$ 应理解为 $f^{-1}(B-C) =A - f^{-1}\left(C\right)$ .   

 

**Proof.** 根据逆像、交并补运算的定义可推出“$\subseteq$” 和 “$\supseteq$”关系成立，从而证明集合相等. 证明过程类似，此处略。  
与像有关的结论更弱一些 (交集的像不一定等于像的交集)：  

**与像有关的命题** 考虑函数$f:A\to B$ . 令$C$ 和 $D$为$A$ 的子集, 则


$$
\begin{align}
(4)& \quad f(C\cup D) = f(C) \cup f(D) \\
(5)& \quad f(C\cap D) \subseteq f(C) \cap f(D)
\end{align}
$$


**Proof.** 根据定义容易证明$(4)$ 等式成立. $(5)$ 根据定义容易证明“$\subseteq$” 成立，反之则不成立, 仅当$f$是单射时左右两个集合才相等. 当$f$不是单射(存在多对一关系)时，可能出现两子集交集的像小于各自像的交集，甚至$C\cap D$为空集的情况.    
**反例1**  定义$f:\mathbb{N} \to \{0,1\}$ 为 $f(x) = x \ \text{mod}\  2$ . 令 $C = \{2, 4\}$ , $D=\{1, 6\}$ .  则  
$C\cap D = \emptyset$ ,  $f(C\cap D)=\emptyset$ , $f\left(C\right)=\{0\}$, $f(D)=\{0,1\}$ ，$f\left(C\right)\cap f(D)=\{0\}$   
**反例2** 令$𝐶=\lbrace 1,2 \rbrace$, $𝐷=\lbrace 1,3\rbrace$ ，设 $𝑓(1)=1$, $𝑓(2)=2$, $𝑓(3)=2$

![](https://imagebed.deepmind.top/img/BA-C0/2.png)





### 单射、满射、双射、反函数、复合函数

**单射的定义**  令$f:A\to B$ 表示一个函数。如果   


$$
f(x_1) = f(x_2) \implies x_1 = x_2  \quad \Bigl(\ x_1 \neq x_2 \implies f(x_1)\neq f(x_2)\ \Bigr)
$$


我们就称$f$是单射的 (**injective**) 或一对一的 (**one-to-one**) 。换句话说，如果对陪域$B$中每个元素 $\forall y \in B$ , 逆像$f^{-1}(\{y\})$ 只包含一个元素或者为空，则我们称$f$是单射函数( **injection**或 **injective function** ).    
  如果$f(A)= B$，则我们称$f$是满射的(**surjective**) 或映成的(**onto**).  换句话说，如果$f$的值域与陪域是相等的，我们就称$f$是满射函数 (**surjection**).    
如果$f$即是单射又是满射，则我们称$f$是双射的(**bijective**) 或 $f$是满射函数 (**bijection**).     

当$f:A\to B$ 是双射函数时，$B$ 中每个元素的逆像 $f^{-1}(\{y\})$ 总是$A$ 中一个唯一的元素. 我们把$f^{-1}$看作一个函数$f^{-1}:B \to A$ , 简写为$f^{-1}(y)$ . 此时我们称$f^{-1}$ 是$f$的反函数 (逆函数，**inverse function**). 注意，仅当$f:A\to B$为双射时，反函数才存在. 例如，对于由表达式$f(x):=x^3$ 定义的双射函数$f:\mathbb{R}\to\mathbb{R}$ ，我们有$f^{-1}(x)=\sqrt[3]{x}$ .    

**复合函数的定义** 考虑函数$f:A\to B$ 和函数 $g:B \to C$. 函数$f$和$g$ 的复合函数 (**composition** of functions)    
$g\circ f: A\to C$ 定义为：   


$$
(g \circ f)(x) := g\bigl(f(x)\bigr)
$$


![](https://imagebed.deepmind.top/img/BA-C0/3.png)



例如，如果函数$f:\mathbb{R}\to\mathbb{R}$ 是 $f(x) := x^3$ 且函数$g:\mathbb{R}\to\mathbb{R}$ 是$g(y):=\sin(y)$ ，则复合函数$(g\circ f)(x) = \sin(x^3)$ .

**命题**  双射函数的复合函数还是双射函数 (composition of bijections is a bijection)

**Proof.** 令$h:A\to C$ 是双射函数$f:A\to B $ 和 $g:B\to C$ 的复合函数，记为$h(x)=(g\circ f)(x)$ .   
先证$h$是单射，即$h(x_1)=h(x_2) \implies x_1 = x_2$ .    
如果$h(x_1)= h(x_2)$ 则有  
$g(f(x_1))=g(f(x_2))$ $\implies$ $f(x_1)=f(x_2)$  (g是单射)   $\implies$ $x_1=x_2$ (f是单射).  $h$是单射得证.   
再证$h$是满射, 即$h(A)=C$  : $\forall z \in C,\ \exists\ x \in A\ s.t.\ h(x)=z $.     
令$z \in C$.  $\because g$是满射   $\therefore $  $\forall z \in C,\ \exists\ y \in B \ s.t.\ g(y)=z$.       
$\because f$是满射 $\therefore$ $\forall y \in B,\exists x \in A\ s.t. f(x)=y$   
$\therefore$ $\forall z \in C,\ \exists x \in A\ s.t.\ g(f(x))=z$ 即 $h(x)=z$ . $h(A)=C$ 得证.  $\square$  


## 关系与等价类 Relations and exquivelence classes

**二元关系的定义** 给定集合$A$ ，$A$上的一个二元关系 (**binary relation**) 是笛卡尔积$A\times A$ 的一个子集$\mathscr{R} \subseteq A\times A$ ，其中的有序对$(a,b)$ 存在某种关系。通常我们写作$a\ \mathscr{R}\ b$ 而不是$(a,b) \in \mathscr{R}$ .     

**二元关系举例** 集合$A := \lbrace 1,2,3 \rbrace$.    
考虑'$<$' 关系，对应的有序对集合是$\bigl\lbrace{(1,2),(1,3),(2,3)\bigr\rbrace}$ . 因为$(1,2)$ 在关系所对应的有序对集合中，所以$1\lt 2$ 成立. 但$3\lt 1$不成立因为$(3,1)$ 不在集合中.    
类似地，'$=$' 关系定义为有序对的集合$\lbrace (1,1),(2,2),(3,3)\rbrace$         
$A\times A$ 的任意子集都是一个关系. 例如我们可以通过$\lbrace(1,2),(2,1),(2,3),(3,1) \rbrace$ 定义一个关系$\dagger$ , 则$1\dagger 2$ 和 $3\dagger  1$ 都成立，但$1\dagger 3$ 不成立. 

**关系的基本性质**  设$\mathscr{R}$是$A$上的二元关系.  我们称$\mathscr{R}$ 是  
$(i)$ **自反的 (Reflexive)** 如果对所有$a\in A$ 都有$a\ \mathscr{R} \ a$ .   
$(ii)$ **对称的 (Symmetric)**  如果 $a\ \mathscr{R}\ b \implies b\ \mathscr{R}\ a$ .    
$(iii)$ **传递的 (Transitive)**  如果 $a\ \mathscr{R}\ b$ 且 $b\ \mathscr{R}\ c \implies a\ \mathscr{R}\ c$ .   
如果$\mathscr{R}$是自反、对称、传递的，我们称$\mathscr{R}$是一个**等价关系 (equivalence relation)** .     

**关系的性质举例**  令$A:=\lbrace 1,2,3 \rbrace$ . $A$上的'$<$' 关系是传递的，但既不是自反的也不是对称的. 定义为$\lbrace (1,1),(1,2),(1,3),(2,2),(2,3),(3,3)\rbrace$ 的'$\le$' 关系是自反的和传递的，但不是对称的.    
最后一个例子：定义一个关系$\star$ 为$\lbrace(1,1),(1,2),(2,1),(2,2),(3,3) \rbrace$. 这个关系是一个等价关系.    
等价关系的作用在于它把一个集合划分成一个个由“等价的”(**equivalent**)元素组成的集合。   
等价关系的典型例子：'模$m$同余'关系把$\mathbb{Z}$划分为$m$个等价类.

### 等价类的定义  

令 $\mathscr{R}$ 是集合$A$上的一个等价关系. 元素 $a\in A$ 的一个等价类是集合$\lbrace x\in A \mid a \ \mathscr{R}\ x	 \rbrace$ , 记为$[a]$.       
集合A在等价关系R下的等价类将集合A分解成了若干个不相交的子集

### 等价类的性质

令$\mathscr{R}$是$A$上的一个等价关系. 

**分解性**  集合A在等价关系$\mathscr{R}$下的所有等价类组成集合$A$的一个划分.   
 (等价关系将$A$分解成互不相交的若干子集，所有等价类的并集是$A$本身且两个不同的等价类交集为空)

**Proof.**   先证覆盖性：对集合中任意元素$x \in A$, 根据等价关系的自反性有$x\ \mathscr{R}\ x$，则$x \in [x]$, 即每个元素$x$都属于自身的等价类$[x]$ ,因此所有等价类必将没有遗漏地覆盖$A$中每个元素，即所有等价类的并集是$A$本身.    
再证互斥性：Two distinct equivalence classes are disjoint. (i.e. have no elements in common)   
对不同的等价类$[a]$和$[b]$ , 假设$[a]$和$[b]$交集不为空，取交集中的一个元素$c$. 我们要推出$[a]=[b]$，用反证法证明$[a]$和$[b]$ 的交集为空。  
因为$c \in [a]$ 且 $c \in [b]$ , 有 $c\ \mathscr{R}\ a$ 且 $c\ \mathscr{R}\ b$ . 由等价关系的对称性和传递性有$a\ \mathscr{R}\ b$.    
假设$x \in [a]$ ，有$x\ \mathscr{R}\ a$. 由传递性有$x\ \mathscr{R}\ b$ , 则$x \in [b]$ .  所以$[a] \subseteq [b]$ .       
类似地，假设$x\in [b]$ 可以推出$[b] \subseteq [a]$.  所以有$[a]=[b]$.    
这与$[a] \neq [b]$ 矛盾，所以假设不成立，即不同的等价类交集为空. $\square$  



![](https://imagebed.deepmind.top/img/BA-C0/4.png)



**划分的唯一性** $A$中的每个元素$a \in A$ 只能属于一个等价类. 

**Proof.** ($i$) 先证每个$a \in A$ 都至少属于一个等价类: 根据等价关系的自反性，$\forall a \in A$, 有$a\ \mathscr{R}\ a$ ，即$A$中的每个元素都与自身存在等价关系，所以每个元素$a$都至少属于它自身的等价类$[a]$.      
$(ii)$ 再证没有元素可以属于两个不同的等价类：上文已证明不同等价类的互斥性.   
所以$A$中每个元素只能属于一个等价类. $\square$          

进一步地，我们有：

**命题**  $a\ \mathscr{R}\ b$  $\iff$ $[a]=[b]$    

**Proof.**  先证"$\impliedby$" :  假设$[a]=[b]$ .  因为$a\ \mathscr{R}\ a$ ($\mathscr{R}$是自反的)，我们有 $a \in [a] = [b]$ . 由$a \in [b]$ 知 $a\ \mathscr{R}\ b$.   
再证"$\implies$"：假设$a\ \mathscr{R}\ b$. 先证$[a] \subseteq [b]$:  取任意$x \in [a]$ ，有$a\ \mathscr{R}\ x$. 由对称性有$x\ \mathscr{R}\ a$.   因为$x\ \mathscr{R}\ a$且$a\ \mathscr{R}\ b$ ，由传递性有$x\ \mathscr{R}\ b$ ，所以$x \in [b]$. 所以有$[a]\subseteq [b]$.  
再证$[a]\supseteq [b]$.   取任意$x \in [b]$ ，有$b\ \mathscr{R}\ x$. 因为$a\ \mathscr{R}\ b$ 且 $b\ \mathscr{R}\ x$ ，由传递性有$a\ \mathscr{R}\ x$ ，所以有$x \in [a]$ . 所以$[b]\subseteq [a]$. 即$[a]\supseteq [b]$ . 所以$[a]=[b]$ .  $\square$    







