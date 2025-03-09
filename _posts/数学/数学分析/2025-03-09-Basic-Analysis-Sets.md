---
title: 分析基础：集合
date: 2025-03-09 16:10:58 +0800
categories:
  - 数学
  - 数学分析
tags:
  - 集合运算
---
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

> **德摩根律 (Demorgan)** 如果$A$ , $B$,  $C$ 为任意三个集合，我们有  
> $1)$  $(B \cup C)^{\complement} = B^{\complement} \cap C^{\complement}$       
> $2)$  $(B \cap C)^{\complement} = B^{\complement} \cup C^{\complement}$   
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
$x \in (A-B) \implies x \in A$ 且 $x \notin B$ ,  $x \in (A-C)$ $\implies x \in A$ 且 $x \notin C$ .   
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
空集与任何集合的交集都为空集，则有 $\bigcap\limits_{m=1}^{\infty}\lbrace{ k\in\mathbb{N} \mid mk < n \rbrace} = \emptyset$ .   
所以 $\bigcup\limits_{n=1}^{\infty}\bigcap\limits_{m=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace = \bigcup\limits_{n=1}^{\infty}\emptyset = \emptyset$.          
交换运算顺序原式变为：


$$
\bigcap_{m=1}^{\infty}\bigcup_{n=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace
$$



给定$m$时，因为$n$没有上界， $k < \dfrac{n}{m}$ 可以取遍所有自然数，则有$\bigcup\limits_{n=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace = \mathbb{N}$.       
所以 $\bigcap\limits_{m=1}^{\infty}\bigcup\limits_{n=1}^{\infty}\lbrace k \in \mathbb{N} \mid mk < n\rbrace = \bigcap\limits_{m=1}^{\infty} \mathbb{N} = \mathbb{N}$.  交换次序后运算结果并不相等。     
