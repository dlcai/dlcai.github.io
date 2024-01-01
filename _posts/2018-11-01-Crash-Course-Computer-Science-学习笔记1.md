---
title: Crash Course Computer Science学习笔记：逻辑门、ALU、寄存器、内存
date: 2018-11-01 00:09:45 +0800
categories: [计算机科学基础, 计算机组成与体系结构]

tags: [notes, cs, cpu, ALU, 寄存器，内存，学习笔记，视频课程]
---


Morse利用继电器的原理发明了电报，实现了人类世界范围内长距离的、即时的通讯  —— 《Code》           
晶体管(transistor) 有两个电极，中间用半导体隔开，控制线连到“门”电极，通过改变“门”的电荷来控制半导体的导电性。         
如今计算机里的晶体管小于50纳米，作为对比，一张纸的厚度大约是10万纳米。        
很多晶体管和半导体的开发在“圣克拉拉谷”（Santa Clara Valley)  在加州的旧金山和圣荷西之间，         
生产半导体最常见的材料是硅(silicon), 所以这个地区被称为“硅谷”(Silicon Valley)           
# 3 Bolean Logic & logic gates 布尔逻辑和逻辑门         

开始抽象之旅：不管底层细节，把精力用来构建更复杂的系统            
用晶体管可以轻松实现真值表的布尔逻辑。            
一个晶体管本身只是控制电的开关，水龙头的比喻：        
![](https://imagebed.deepmind.top/img/1.jpg)







​    

把控制线当作输入，底部电极当作输出，一个晶体管对应的真值表是          
![](https://imagebed.deepmind.top/img/2.jpg)









稍加修改，实现NOT        
![](https://imagebed.deepmind.top/img/3.png)









输入1输出0的原理比喻:  家里的水都从一个大管子排走了，所以打开淋浴头一点水压也没有了         
![](https://imagebed.deepmind.top/img/4.jpg)









当输入是0，电流没法接地，只能从输出流出去，实现了输出1。至此只用一个晶体管实现了非门            
![](https://imagebed.deepmind.top/img/5.png)









串联两个晶体管，实现AND 与门         
![](https://imagebed.deepmind.top/img/6.png)









并联两个晶体管，实现OR 或门      
![](https://imagebed.deepmind.top/img/7.png)











XOR与OR的不同：两输入都为true时输出是false，因此需要先用AND门筛选出输出全1的情况，      
再用NOT门变为false，最后和OR的输出一起连到第二个AND门，强行使最终输出为false；       
其他情况下NOT门输出均为true，连到AND不影响OR门的输出结果，最终输出与OR一致。        
![](https://imagebed.deepmind.top/img/8.png)















再次向上抽象       
![](https://imagebed.deepmind.top/img/9.png)















​         

#  4 二进制        
硬盘厂商说的8T是指8000000000000字节，但是计算机对硬盘容量的计算方式不同，采用二进制，每1024进一个单位，    
所以有8000000000000b≈7812500000K≈7629395M≈7504G≈7.32T        
补码(时钟、模的概念）移码 IEEE754浮点数等知识         

#  5  ALU   How Computers Calculate
用布尔逻辑门做一个简单的ALU电路，功能和Intel 74181一样。                  
最简单的加法电路，AB两个bit输入和一个bit输出，共有4种输入情况。                     
前三种情况和XOR门的逻辑完全一样。         
![](https://imagebed.deepmind.top/img/10.png)











输入是1，1时输出10用一个bit存不下，需要一根额外的输出线代表“进位”(carry)            
AND门刚好能做这个事！ 根据AB的输入表示进位情况。          
XOR门计算sum, AND门输出carry,  从而组成“半加器”         
![](https://imagebed.deepmind.top/img/11.png)









进一步抽象，把半加器封装成一个单独的组件：       
![](https://imagebed.deepmind.top/img/12.png)







处理超过1+1的运算时，需要全加器，要接收前一列进位，需要三个输入A + B + C     
A + B相加进位C1,  AB之和S + 与前一列的进位C产生C2,      
C1和C2不可能同时为1, 因为若C1是1 => AB都是1 => S是0 => S + C的进位C2必为0            
C1和C2只要有一个是1都会向下一列进位，所以OR门连接C1C2正好实现了全加器的进位。                
用**两个半加器**和**一个OR门**组成全加器        
![](https://imagebed.deepmind.top/img/13.png)









进一步抽象，把全加器封装成一个单独的组件         
![](https://imagebed.deepmind.top/img/14.png)









​         

## 制作8位加法器        
最低位A0+B0没有前一列的进位，只需一个半加器，其余列相加用全加器       
![](https://imagebed.deepmind.top/img/15.png)













前一个全加器的进位连到下一个全加器的输入，所以叫**8位行波进位加法器(8-bit ripple carry adder)**                  
如果想避免溢出(overflows) 可以增加更多全加器来操作16、32位乃至更多位的数字，代价是更多逻辑门，           
另一个缺点是，每次行波进位都要多消耗一点时间，如今的运算都是每秒几十亿次的量级，行波进位的电路性能不够，              
现代计算机的加法电路采用“超前进位加法器”（carry-look-ahead adder)          
ALU的算术单元通常会支持这8种操作：        
![](https://imagebed.deepmind.top/img/16.png)












简单的ALU没有专门的电路来处理乘法和除法，乘法用多次加法来实现，例如12 x 5就是把12加5次。          
许多简单处理器，比如恒温器 (thermostat)、电视遥控器(TV remote)和微波炉 (microwave) 都这样做；       
笔记本电脑和手机有更好的处理器，算术单元有专门的乘法电路，there's no magic 乘法电路只是有更多逻辑门            

## 逻辑单元 Logic Unit   
执行AND, OR, NOT等逻辑操作，也能做简单的数值测试，比如判断一个数是不是负数。          
例如，检测ALU输出是否为0的电路：一堆OR门最后加个NOT门           
![](https://imagebed.deepmind.top/img/17.png)











**ALU抽象：一个V符号**。高级ALU有更多Flag标志，但这3个flag是普遍的。       
![](https://imagebed.deepmind.top/img/18.png)















​     

#  6 寄存器和内存  Registers and RAM      
存储1的电路：把OR门的输出连到其中一个输入；存储0的电路：把AND门的输出连到其中一个输入        
![](https://imagebed.deepmind.top/img/20.png)











SET和RESET都为0，输出上次保存的结果，不受输入影响（OR的输出取决于OUTPUT, AND的输出取决于OR)         
RESET为1，相当于把输出置为0       
SET = 1, RESET = 0, 相当于把输出置为1         
![](https://imagebed.deepmind.top/img/21.png)









加一段逻辑门，使得:      
关闭写入时，相当于RS都为0（通过把RS连接到两个AND门，由WRITE ENABLE线控制，WE=0时，输出不受影响）         
允许写入WE=1时，       
数据输入1相当于SET = 1, RESET = 0，即RS锁存器把输出置为1        
数据输入0相当于RESET = 1, 即RS锁存器把输出置为0        
![](https://imagebed.deepmind.top/img/22.png)









再提升一层抽象：**门锁（Gated Latch)**  
并排放8个锁存器，可以存8位信息，一组这样的锁存器称为寄存器 (register), 寄存器能存数字的位数称为位宽。              
早期电脑用8位寄存器，然后16位、32位，如今很多计算机都有64位宽的寄存器。                
写入寄存器前，要先ENABLE所有的锁存器，可以只用一根线连接所有的WE输入1，用8根线发完数据后把WE设回0      
![](https://imagebed.deepmind.top/img/23.png)









如果只需存很少的位，锁存器排成一列放置就够用了。      
64位寄存器需要64根数据输入线，64根连到输出端，1根WE线，共129根线。       
如果存256位需要513根，每增加一个位，输入输出端都要多浪费两根线，解决方法是矩阵。      
![](https://imagebed.deepmind.top/img/24.png)











如何只选中并启用行列交叉处的某一个锁存器？用AND门！         
![](https://imagebed.deepmind.top/img/25.png)













每次只能访问一个锁存器，只有一个被启用来存取数据，故可以用一根数据输入线连接所有256个锁存器，         
可以多加一根READ ENABLE线来允许读出，采用WE前面相同的AND门控制，数据读出和数据输入共享一根线传输。         
矩阵方式只需16+16根地址线、1根数据输入/输出线，WE和RE线各1根，加起来仅需35根，节省了很多数据线；       
将n位地址转成2^n行和列选中（例如16x16内存表示行列只需4位，共8位地址）需要多路复用器（multiplexer)        
![](https://imagebed.deepmind.top/img/26.png)











这里MUX指的是n to 2ⁿ **译码器**，2 to 4 Line Decoder门电路实现原理如图。             
根据真值表，哪条线输出为1，连接电路使得对应输入下该条线的AND门输入全为1即可          
![](https://imagebed.deepmind.top/img/27.png)









16x16内存模块抽象：        
![](https://imagebed.deepmind.top/img/28.png)









相比8位寄存器，这种串行方式读取一个字节太耗时，解决方式是把8个矩阵排列的内存模块并成一行，           
分别寻址同时访问1位锁存器，实现8位并行读写        
![](https://imagebed.deepmind.top/img/29.png)











存储器抽象：    
![](https://imagebed.deepmind.top/img/30.png)















8位只能寻址256个字节，32位地址可以寻址约42亿字节（4GB)
SRAM一个位的电路包含不少晶体管，速度快但造价昂贵，一般用来做CPU芯片中的高速缓存。                 
DRAM存储一个位只需要一个电容和一个晶体管，数据存在电容里，电容会有电的泄露、 损失状态，            
故需要对电容状态进行保持和动态刷新，因此速度慢，但造价便宜，容量也大得多，常用来做内存。                   
1980年代的RAM       
![](https://imagebed.deepmind.top/img/31.png)













每个芯片有32个方格，所以每个芯片约有100万位。80年代的RAM只能存储约104万字节，仅1MB内存。                       
![](https://imagebed.deepmind.top/img/32.png)












计算机底层的组成大多很简单，精妙之处是一层层的抽象。        