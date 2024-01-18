---
title: Apostol微积分Ⅰ基础篇P3 实数系公理之域公理
date: 2023-07-01 02:15:35 +0800
categories: [数学,微积分]
tags: [微积分基础,实数理论]
---

## I 3.1 实数公理系统的意义

利用有理数构造实数的工作完成之后，我们就可以反过来，看能不能先定义实数，再把有理数、整数等概念当成「特殊情况」来处理。这样可以把实数集从繁杂的构造理论中解脱出来，让我们更好的把握实数集的性质。1899 年，Hilbert（1862-1943）提出了实数公理系统，直接用「数」这个概念对实数集进行了定义。「数」可看成是存在着四则运算和序关系的集合中的元素。实数公理系统的意义，就是描述我们心目中认为的实数集合的模样。本书用10条公理把实数集定义为完备有序域 (**complete ordered field**) 。实数的所有性质都可以从10条公理推导出来。若采用构造方法来定义实数，10条公理所描述的性质必须作为定理予以证明。

## I 3.2 域公理

我们假定实数集$R$上存在加法和乘法两种运算，使得对每对实数$x$和$y$, 我们能做出$x$和$y$的和，以及x和y的积。这个和是用$x+y$表示的另一个实数，这个积是由$xy$或$x \cdot y$表示的另一个实数。假定和$x+y$及积$xy$是由$x$及$y$唯一确定的。换句话说，给定$x$与$y$，恰存在一个实数$x+y$，也恰存在另一个实数$xy$。符号$+$和$\cdot$ 除了在公理中表示运算以外，我们不附加任何特殊的含义。   

**公理1**  &nbsp;&nbsp; **交换律.**	$x + y = y + x, xy = yx$    
**公理2**  &nbsp;&nbsp; **结合律.**    $x+(y+z)=(x+y)+z, x(yz) = (xy)z$  
**公理3**  &nbsp;&nbsp; **分配律.**	$x(y+z)=xy+xz$   
**公理4**  &nbsp;&nbsp; **单位元(Identity Elements)的存在.** 	存在$0$和$1$表示的两个不同实数，使得对于每个实数$x$我们有$x+0=x$ 和$1*x=x$.   
**公理5** &nbsp;&nbsp; **负数(相反数,加法逆元) 的存在.**  对每个实数$x$, 存在一个实数$y$，使得$x+y=0$.  
**公理6** &nbsp;&nbsp;  **倒数的存在.** 	对每个实数$x \ne 0$, 存在一个实数$y$，使得$xy=1$.  
注：公理5和6中的数0和1就是公理4中的单位元。  
由这6条域公理可以导出初等代数所有常见的定律。最重要的定律作为定理列在下面。符号$a,b,c,d$ 表示任意实数。    
**定理I.1**  &nbsp;&nbsp;  **加法消去律.**    如果$a+b=a+c$，则$b = c$. (这表明公理4中的0是唯一的)      
**定理I.2**  &nbsp;&nbsp;  **减法的可能性.**  给定$a$和$b$，恰好存在一个$x$使得$a+x=b$.  这个$x$ 用$b-a$表示. 特别地，$0-a$被简写成$-a$，称为$a$ 的负数(相反数,加法逆元) .  
**定理I.3**  &nbsp;&nbsp; $b-a=b+(-a)$  
**定理I.4**  &nbsp;&nbsp; $-(-a)=a$  
**定理I.5**  &nbsp;&nbsp; $a(b-c)=ab-ac$   
**定理I.6**  &nbsp;&nbsp; $0 \cdot a = a \cdot 0 = 0$    
**定理I.7**  &nbsp;&nbsp;  **乘法消去律.**    如果 $ab=ac$ 且 $a \neq 0$, 则$b=c$. (这表明公理4中的1是唯一的)   
**定理I.8**  &nbsp;&nbsp;  **除法的可能性.**  给定$a$和$b$ 且$a \neq 0$, 恰好存在一个$x$使得$ax=b$, 这个$x$用$b/a$ 或$\dfrac{b}{a}$ 表示，称为$b$与$a$的商。特别地$1/a$（或$a^{-1}$） 称为$a$的倒数.    
**定理I.9** &nbsp;&nbsp;  如果$a \neq 0$, 则$b/a = b \cdot a^{-1}$.   
**定理I.10** &nbsp;&nbsp; 如果$a \neq 0$, 则$(a^{-1})^{-1}=a$.    
**定理I.11** &nbsp;&nbsp; 如果$ab=0$，则 $a=0$ 或 $b=0$.   
**定理I.12** &nbsp;&nbsp; $(-a)b=-(ab)$，以及$(-a)(-b)=ab$.      
**定理I.13** &nbsp;&nbsp; 如果$b\neq0$ 且$d\neq0$，则有$\dfrac{a}{b}+\dfrac{c}{d}=\dfrac{ad+bc}{bd}$.        

**定理I.14** &nbsp;&nbsp; 如果$b\neq0$ 且$d\neq0$，则有$\dfrac{a}{b}\cdot\dfrac{c}{d}=\dfrac{ac}{bd}$.    

**定理I.15** &nbsp;&nbsp; 如果$b\neq0, c\neq0$和$d\neq0$，则有$\dfrac{a/b}{c/d}=\dfrac{ad}{bc}$.



**定理I.1证明：** 给定$a+b=a+c$ ，由公理5和1，存在实数$y$ 使得$y+a = 0$. 因为和是唯一确定的，有$y+(a+b)=y+(a+c)$ . 由公理2结合律有$(y+a)+b=(y+a)+c$ 即$0+b=0+c$. 由公理4有 $0+b=b$ 及$0+c=c$, 所以$b=c$得证. 加法消去律表明了只有一个实数具有公理4中单位元0的性质。假设存在$0'$也具有单位元性质，则有$0+0'=0$ 和$0+0=0$ 同时成立，即$0+0'=0+0$ , 由加法消去律有$0'=0$, 得证.    
**定理I.2证明：** 给定$a$和$b$, 由公理5负数的存在，存在一个实数$y$ 使得$a+y=0$. 令$x = y+b$, 则$a+x=a+(y+b)=(a+y)+b=0+b=b$. 所以至少存在一个$x$，使得$a+x=b$. 假设存在另一实数$x'$ 使得$a+x'=b$，则$a+x=a+x'$. 由定理I.1知$x=x'$，故这样的$x$至多只有一个。所以恰好存在一个$x$使得$a+x=b$.   
**定理I.3证明：** 令$x=b-a$,  $y=b+(-a)$, 要证$x=y$. 由定理I.2中$b-a$的定义有$x+a=b$. $y+a=b+(-a)+a=b+[(-a)+a]=b+0=b$. 所以$x+a=y+a$. 由定理I.1加法消去律$x=y$得证.    
**定理I.4证明：** 根据定理I.2, 恰好存在一个$x$, 使得$(-a)+x=0$. 这个$x$用$0-(-a)$表示. 由定理I.3有$0-(-a)=0+[-(-a)]=-(-a)$, 即$x=-(-a)$. $(-a)+x=0$ 两边加$a$得$a+(-a)+x=a+0$. 由定理I.2知$-a$是$a$的负数，$a+(-a)=0$, 所以有$0+x=a+0$ 即$x=a$. 所以$-(-a)=a$ 得证.    
**定理I.5证明**:  由定理I.2   $ab-ac$ 是唯一使得 $ac+x=ab$ 的实数$x$.     
又因为     

$$
\begin{align}
ac + a(b-c) &= ac + a(b+(-c)) \\
&= ac + ab + a(-c) \\  
&= ac + a(-c) + ab \\
&= a[c+(-c)] + ab \\
&= a \cdot 0 + ab \\
&= a(0+b) \\
&= ab
\end{align}
$$

所以 $a(b-c)$ 就是 $ab-ac$，得证.   
**定理I.6证明：** 由公理4知0是加法单位元，则有  


$$
\begin{align}
0 \cdot a &= (0+0) \cdot a  \\
&= 0 \cdot a + 0 \cdot a \hspace{2em}(公理3分配律) 
\end{align}
$$

等式左边 $0 \cdot a = 0 \cdot a +0$ , 所以有 $0 \cdot a + 0 = 0 \cdot a + 0 \cdot a $    
由定理I.7加法消去律可得 $0 \cdot a = 0$     
又因公理1乘法满足交换律，有 $0 \cdot a = a \cdot 0 = 0$ 得证.    
**定理I.7证明：** 给定$ab=ac$ 且 $a \neq 0$，由公理6 (倒数的存在) 和公理1 (乘法满足交换律)，存在实数 $y$ 使得$ya =1$. 根据乘法运算的定义积是唯一的，有$y(ab) = y(ac)$ 由公理2乘法满足结合律，有$(ya)b=(ya)c$ 即$1 \cdot b = 1 \cdot c$ 由公理4知1是乘法单位元，即$1 \cdot b = b\text{, } 1 \cdot c = c$ 所以 $b=c$ 得证. 乘法消去律表明仅存在一个实数具有公理4中单位元的性质。假设存在另一实数$1'$也是乘法单位元，则有 $1 \cdot 1' = 1$ 和$1 \cdot 1 = 1$ 即 $1 \cdot 1' = 1 \cdot 1$ 又由公理4有$1' = 1$ 乘法单位元的唯一性得证.    
**定理I.8证明：** 给定$a$和$b$ 且$a \neq 0$，由公理6 (倒数的存在)，存在一个实数 $y$ 使得 $ay=1$. 令$x=yb$, 则$ax=a(yb)=(ay)b = 1 \cdot b = b$. 所以至少存在一个 $x$ 使得$ax=b$. 假设存在另一实数$x'$ 使得$ax'=b$, 则有$ax'=ax$. 由定理I.7乘法消去律有$x'=x$. 故这样的$x$至多只有一个。所以恰好存在一个$x$使得$ax=b$.即商的唯一性得证.     
**定理I.9证明：** 令$x=b/a, y=b \cdot a^{-1}$，要证$x=y$. 由定理I.8中商的定义有$xa=b$. $ya=(b \cdot a^{-1}) \cdot a = b \cdot (a^{-1} \cdot a)=b \cdot 1 = b$. 所以有$xa = ya$. 由定理I.7乘法消去律有$x=y$ 得证.  
**定理I.10证明：** 根据定理I.8，恰好存在一个$x$ 使得$a^{-1}x=1$, $x$用$1/a^{-1}$ 表示. 由定理I.9有$1/a^{-1}=1 \cdot (a^{-1})^{-1} = (a^{-1})^{-1}$, 即$x=(a^{-1})^{-1}$. 又由倒数的定义有$a^{-1}a=aa^{-1} =1$ . 因为$x$是唯一的，所以$x=a$.所以 $(a^{-1})^{-1}=a$ 得证.    
**定理I.11证明：** 只须证明逆否命题“如果$a\neq0$且$b\neq0$, 则$ab\neq0$.”。给定$a\neq0$且$b\neq0$, 假设$ab=0$成立. 由公理6和定理I.8倒数的定义, 存在唯一的$b^{-1}$ 使得$b \cdot b^{-1}$= 1. 等式两边同乘$b^{-1}$有 $abb^{-1} = 0 \cdot b^{-1}$ 即$a \cdot 1 = 0 \cdot b^{-1}$ 由定理I.6知$0 \cdot b^{-1}=0$ 由公理4知1是加法单位元$a\cdot1=a$ 从而推出$a=0$ 与给定$a\neq0$矛盾，故假设不成立，所以$ab\neq0$, 逆否命题为真，原命题得证.     


**定理I.12证明：** 先证$(-a)b=-(ab)$.      


$$
\begin{align}
0 \cdot b = 0 \quad (\mathsf{定理I.6}) \hspace{-12em}\\
&\Longrightarrow \quad [a+(-a)]\cdot b = 0 \quad (\mathsf{定理I.2相反数的定义})\\
&\Longrightarrow \quad ab +(-a)b = 0 \quad(\mathsf{公理3分配律}) 　\\
&\Longrightarrow \quad (-a)b = -(ab) \quad(\mathsf{定理I.2相反数的定义}) \quad\#
\end{align}
$$

​      



再证$(-a)(-b)=ab$.      

$$
\begin{align}
(-a) \cdot 0 = 0 \quad (\mathsf{定理I.6}) \hspace{-11.8em}\\
&\Longrightarrow (-a)\cdot[b+(-b)] = 0 \quad(\mathsf{定理I.2相反数的定义}) \\
&\Longrightarrow (-a)b + (-a)(-b) = 0 \quad(\mathsf{公理3分配律}) \\
&\Longrightarrow -(ab) + (-a)(-b) = 0 \quad(\mathsf{已证结论}\mathsf{(-a)b=-(ab)}) \\
&\Longrightarrow (-a)(-b) = ab \quad(\mathsf{定理I.2相反数的定义}) \quad\#
\end{align}
$$

​          


**定理I.13证明：**         

$$
\begin{align}
\dfrac{a}{b}+\dfrac{c}{d} \hspace{-4.5em}\\
&= a \cdot b^{-1} + c \cdot d^{-1} \quad (\mathsf{定理I.9}) \\ 
&= a \cdot b^{-1}\cdot 1+ c \cdot d^{-1}\cdot 1 \quad (\mathsf{公理4}) \\ 
&= a \cdot b^{-1} \cdot(d\cdot d^{-1})+ c \cdot d^{-1}\cdot(b\cdot b^{-1}) \quad (\mathsf{定理I.8}) \\ 
&= ad \cdot(b^{-1} \cdot d^{-1})+ bc \cdot (b^{-1}\cdot d^{-1}) \quad (\mathsf{公理1和2交换律和结合律}) \\
&= (ad+bc)(b^{-1}d^{-1}) \quad (\mathsf{公理3分配律}) \quad \#
\end{align}
$$



下面证明$b^{-1}d^{-1}= (bd)^{-1}$ (逆元的乘积等于乘积的逆元). 由定理I.8倒数的定义有$b\cdot b^{-1}=d\cdot d^{-1} =1$ 则$(b\cdot b^{-1}) \cdot (d\cdot d^{-1}) =1 \cdot1 = 1$ 由公理1-2乘法交换律和结合律有$bd \cdot (b^{-1}d^{-1})=1$ 由定理I.8倒数的定义知$b^{-1}d^{-1}$就是 $bd$ 的倒数$(bd)^{-1}$. 命题得证.     
又由定理I.9有$(ad+bc)(b^{-1}d^{-1})=(ad+bc)(bd)^{-1}=\dfrac{ad+bc}{bd} \ \text{\#}$.           





**定理I.14证明：**     

$$
\begin{align}
\dfrac{a}{b}\cdot \dfrac{c}{d} \hspace{-3.7em}\\
&= a \cdot b^{-1} \cdot c \cdot d^{-1} \quad (\mathsf{定理I.9}) \\  
&= (ac) \cdot (b^{-1}  d^{-1}) \quad (\mathsf{公理1,2交换律和结合律})\\
&= (ac) \cdot (bd)^{-1} \quad (\mathsf{定理I.13已证结论})\\
& = \dfrac{ac}{bd} \quad (\mathsf{定理I.9}) \quad \#
\end{align}
$$

**定理I.15证明：**     

$$
\begin{align}
\dfrac{a/b}{c/d} \hspace{-3.4em}\\
&= \dfrac{a \cdot b^{-1}}{c \cdot d^{-1}} \quad (\mathsf{定理I.9})\\
&= a \cdot b^{-1} \cdot (c \cdot d^{-1})^{-1} \quad (\mathsf{定理I.9}) \\
&= a \cdot b^{-1} \cdot [c^{-1} \cdot (d^{-1})^{-1}] \quad (\mathsf{定理I.13已证结论}) \\
& = a \cdot b^{-1} \cdot (c^{-1} \cdot d) \quad (\mathsf{定理I.10}) \\ 
& = ad \cdot (b^{-1}c^{-1}) \quad (\mathsf{公理1,2交换律和结合律}) \\
& = ad \cdot (bc)^{-1} \quad(\mathsf{定理I.13已证结论}) \\
& = \dfrac{ad}{bc} \quad (\mathsf{定理I.9}) \quad \#
\end{align}
$$
