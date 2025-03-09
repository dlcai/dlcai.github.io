---
title: 分析基础：数学归纳法
date: 2025-03-09 17:21:27 +0800
categories:
  - 数学
  - 数学分析
tags:
  - 良序原理
  - 数学归纳法
  - 强归纳法
  - 算术基本定理
---
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

有时不把1作为base case更方便，只需改变初始值的记号即可。归纳步骤“$P(n)$ 成立 $\implies P(n+1)$ ” 中的“$P(n)$ 成立” 的假设称为归纳假设.   


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
$(i)$ $n = 2$ 时，2本身就是素数，显然成立。  
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