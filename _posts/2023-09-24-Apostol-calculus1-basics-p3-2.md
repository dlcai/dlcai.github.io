---
title: Apostol微积分Ⅰ基础篇P3 实数系公理之序公理
date: 2023-09-24 04:46:23 +0800
categories: [数学,微积分]
tags: [微积分基础,实数理论]
---

## I 3.4 序公理

这组公理在实数中建立了次序，使我们能断言一个实数比另一个实数大还是小。我们通过一组关于“正数性”概念的公理来引入次序性质，根据正数性定义“大于”或“小于”这样一些术语。  
假定有一个称为正数集合的子集 $R^{+}\subset R$ , 满足以下三条序公理：   
**公理7**&nbsp;&nbsp; 如果 $x$ 和 $y$ 在$R^{+}$ 中，则$x+y$ 和 $xy$ 也在$R^{+}$ 中.    
**公理8** &nbsp; 对任意实数$x \neq 0$, 不是$x \in R^{+}$ 就是 $-x \in R^{+}$, 但两者不会同时成立.  （非零实数非正即负）  
**公理9**&nbsp; &nbsp; $0 \notin R^{+}$.       
我们现在可以定义符号$\lt , \gt , \le$ 和$\ge$ 如下：       
          
$$
\begin{align}
x<y \quad &\mathsf{即} \quad y-x \ \mathsf{是正的}; \quad(\mathsf{用差的正数性来定义实数的大小关系})\\
y>x \quad &\mathsf{即} \quad x<y; \\
x\le y \quad &\mathsf{即}\quad \mathsf{不是}\  x < y \ \mathsf{就是}\ x=y; \\   
y \ge x \quad &\mathsf{即} \quad x \le y.
\end{align}
$$

​       

于是，当且仅当$x$是正的时我们有$x>0$. (代入以上定义$x>0$即$0<x$即$x-0$是正的，由定理I.3有$x-0=x+(-0)$. 由定理I.2有$0+(-0)=0$, 由公理4有 $0+0=0$,  所以由定理I.1加法消去律有$-0 = 0$, 则$x-0=x+(-0)=x+0=x$ .即$x$是正的 ).  如果$x<0$ 我们说$x$ 是负的. (代入定义$x<0$即$0-x$是正的即$-x$是正的, 由公理8知$x$是负的). 如果$x\ge0$，我们说$x$是非负的.(代入定义$x\ge 0$ 即$0 \le x$ 即不是$0<x$ 就是$0=x$此时$x$是正的或者$x=0$即$x$是非负的).    
例如$x<y,\ y<z$ 这样的联立不等式经常简写为$x<y<z$. 对于复合不等式$x\le y<z,\ x<y\le z,\ x\le y \le z$ 也可以类似地解释为联立不等式的简写形式。    
由次序公理我们可以推出计算不等式的所有常用规则，最重要的规则作为定理列出如下。  

**定理I.16**&nbsp;&nbsp;**三歧性定律** (Trichotomy Law)  对任意实数$a$和$b$，有且仅有$a < b,\ b<a,\ a=b$ 三个关系中的一个成立.  
**定理I.17**&nbsp;&nbsp;**传递律** (Transitive Law) 如果$a<b,\ b<c$ ，则 $a<c$.    
**定理I.18**&nbsp;&nbsp;如果$a<b$，则$a+c<b+c$.   
**定理I.19**&nbsp;&nbsp;如果$a<b$ 且 $c>0$，则$ac<bc$.    
**定理I.20**&nbsp;&nbsp;如果$a\ne0$，则$a^2>0$.    
**定理I.21**&nbsp;&nbsp; $1>0$.  
**定理I.22**&nbsp;&nbsp;如果$a<b$ 且 $c < 0$, 则$ac>bc$.   
**定理I.23**&nbsp;&nbsp;如果$a<b$，则$-a>-b$. 特别地，如果$a<0$，则$-a>0$.   
**定理I.24**&nbsp;&nbsp;如果$ab>0$，则$a$ 和 $ b$ 都为正或者都为负.
**定理I.25**&nbsp;&nbsp;如果$a<b$ 且$c<d$,  则$a+c<b+d$.   



**定理I.16证明：** 令$x=b-a$. 如果$x=0$，则$b-a=0=-0=-(b-a)=a-b$.  ( $b-a$加$-(b-a)$等于$0$, $b-a$ 加$a-b$ 也等于$0$, 由差的唯一性知两者相等) 由公理9，$b-a$ 不是正的，$a-b$ 也不是正的，所以不能有$a<b$ 或 $b<a$；等式 $b-a=0$ 两边加$a$得$b+(-a)+a=0+a$ 即此时只有 $a=b$ 成立.    
如果$x \ne 0$，由公理8，不是$b-a$ 为正，就是$a-b$ 为正，但两者不会同时成立，由符号定义即 $a<b$, $b<a$ 两者有且仅有一个成立.综上，$a < b,\ b<a,\ a=b$ 三个关系中有且仅有一个成立.  $\#$             
**定理I.17证明：** 如果$a<b$ 且 $b<c$  即 $b-a>0$ 且 $c-b>0$.  由公理7, 两式相加有$(b-a)+(c-b)>0$ 即$c-a>0$. 由符号定义有$a<c$. $\#$    
**定理I.18证明：** 令$y=b+c,x=a+c$. 则$y-x=(b+c)-(a+c)=b+c-a-c=b-a$ . 如果$a<b$ 由符号定义即$b-a>0$ 即 $y-x>0$ 即 $x<y$ 则 $a+c<b+c$. $\#$      
**定理I.19证明：** 由符号定义，$a<b$ 即 $b-a>0$. 如果$c>0$, 由序公理7有$(b-a)c>0$. 由定理I.5减法分配律有$bc-ac>0$ 即 $ac < bc$. $\#$    
**定理I.20证明：** 如果$a>0$, 由公理7有 $a \cdot a> 0$ 即$a^2>0$. 如果$a<0$, 即$0-a>0$. 则$-a>0$. 由公理7有$(-a)(-a)>0$. 由定理I.12知$(-a)(-a)=a \cdot a=a^2$. 则 $a^2>0$ 也成立. $\#$         
**定理I.21证明：** 已知$1\ne0$,  应用定理I.20, 取$a=1$， 则$1^2 = 1\cdot1 >0$ 即$1>0$. $\#$      
**定理I.22证明：** 如果$c<0$ 即$0-c=-c>0$ . 由定理I.19有$a(-c) < b(-c)$. 由定理I.12知$-ac<-bc$ 即 $-bc-(-ac)>0$. 由定理I.4知$-bc+ac>0$ 即 $ac-bc>0$ 由符号定义即$bc<ac$ 即$ac>bc$. $\#$     
**定理I.23证明：**如果$a<b$, 即 $b-a>0$,  则 $-a-(-b)=b-a$ > 0.  由符号定义$-b<-a$ 即$-a>-b$ 得证. 特别地，取$b=0$. 如果$a<0$, 则$-a>0$. $\#$        
**定理I.24证明：**由定理I.6知 $0$乘任意实数都得$0$, 如果$a=0$ 或 $b=0$ 则$ab=0$ 由公理9知$ab$ 不是正数，与$ab>0$ 矛盾. 因此$a$和$b$ 都不为0.  当 $a>0$ 时，如果$b<0$, 由定理I.23知$-b>0$. 则由公理7知$a(-b)>0$ 即$-ab>0$. 由公理8推出$ab$ 是负数，与$ab>0$矛盾. 所以$a>0$时必有 $b>0$. 当 $a<0$ 时，由定理I.23知$-a>0$. 如果$b>0$, 由公理7知$(-a)b>0$ 即$-ab>0$, 与$ab>0$ 矛盾.  所以$a<0$时必有 $b<0$. 所以$ab>0$ 时$a$ 和 $ b$ 都为正或者都为负. $\#$     
**定理I.25证明：** 如果$a<b$ 且$c<d$,  由符号定义有 $b-a>0$ 且$d-c>0$. 则由公理7有 $(b-a)+(d-c)=b+d-a-c=(b+d)-(a+c)>0$. 即 $a+c<b+d$. $\#$     
