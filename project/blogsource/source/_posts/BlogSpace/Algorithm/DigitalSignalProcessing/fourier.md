---
title: Fourier Transform(傅里叶变换)
date: 2018-06-20 17:03:01
tags: BlogSpace  
categories:   
- BlogSpace 
- Algorithm
- DigitalSignalProcessing  

---

一、傅里叶级数
---
周期函数f(t)可由三角函数的线性组合来表示，若f(t)的周期为$T_1$,角频率$w_1=\frac{2\pi}{T_1}$,频率$f_1=\frac{1}{T_1}$
三角函数形式：
$$f(t)=a_0+\sum_{n=1}^\infty[{a_n}cos(nw_1t)+b_nsin(nw_1t)]$$
<!--more-->
各次谐波的分量：
直流分量：$a_0=\frac{1}{T_1}\int_{t_0}^{t_0+T_1}{f(t)dt}$
余弦分量的幅度：$a_n=\frac{2}{T_1}\int_{t_0}^{t_0+T_1}f(t)cos(nw_1t)dt$
正弦分量的幅度：$b_n=\frac{2}{T_1}\int_{t_0}^{t_0+T_1}f(t)sin(nw_1t)dt$
不是所有的周期函数都能进行傅里叶级数展开，需要满足充分条件，“狄里赫利(Dirichlet)条件”：
（1）在一周期内，如果间断点存在，则间断点的数目应是有限个；
（2）在一周期内，极大值和极小值的数目应是有限个；
（3）在一周期内，信号是绝对可积得，即$\int_{t_0}^{t_0+T_1}|f(t)|dt$等于有限值（$T_1$为周期）。
一般周期信号都能满足这一条件。

二、z变换
---
1、z变换
$$X(z) = \sum_{n=-\infty}^\infty{x(n)z^{-n}}$$
2、逆变换
$$x(n)=\frac{1}{2{\pi}j}\oint_c{X(z)z^{n-1}dz}$$
级数收敛的充要条件：满足绝对可和条件，即：
$$\sum_{n=-\infty}^\infty|x(n)z^{-n}|=M<\infty$$
注：序列x(n)如果不是绝对可和的，则其z变换不存在
级数收敛性判别法（达兰贝尔判别法）：
对任意求和式$\sum_{n=-\infty}^\infty|a_n|$（例如，这里的$\sum_{n=-\infty}^\infty|x(n)z^{-n}|$），有
$$lim_{n\to\infty}|\frac{a_{n+1}}{a_n}|=l$$
l<1,级数收敛  
l>1,级数发散  
l=1,不能确定  
3、常见性质和定理

详细请看书籍
<table>
<tr><td>性质或定理
    <td>序列
    <td>z变换
<tr><td>线性
    <td>$ax(n)+bh(x)$
    <td>$aX(z)+bH(z)$
<tr><td>序列移位
    <td>$x(n-m)$
    <td>$z^{-m}X(z)$
<tr><td>乘指数序列
    <td>$a^nx(n)$
    <td>$X(\frac{z}{a})$
<tr><td>时域卷积定理
    <td>$x(n)*h(n)$
    <td>$X(z)H(z)$
<tr><td>z域复卷积定理
    <td>$x(n)h(n)$
    <td>$\frac{1}{2\pi i}\oint_cX(v)H(\frac{z}{v})v^{-1}$
</table>

三、离散时间傅里叶变换（DTFT）
---
$$X(e^{jw}) = DTFT[x(n)] = \sum_{n=-\infty}^{\infty}x(n)e^{-jwn}$$
$$x(n) = IDTFT[X(e^{jw}) ] = \frac{1}{2\pi}\int_{-\pi}^{\pi}X(e^{jw})dw$$
注：
1、时域x(n)是离散的，则频域$X(e^{jw})$一定时周期的
2、$X(e^{jwn})$是序列x(n)的频谱密度，简称频谱。可分解为模和相位或实部和虚部如下
$$X(e^{jw})=|X(e^{jw})|e^{jarg[X(e^{jw})]}=Re[X(e^{jw})]+jIm[X(e^{jw})]$$


四、周期序列的傅里级数（DFS）
---
$\widetilde{x}(n)$表示一个周期为N的周期序列，即
$$\widetilde{x}(n) = \widetilde{x}(n+rN)$$
N为正整数，r为任意整数。
$$\widetilde{X}(k)=DFS[\widetilde{x}(n)]=\sum_{n=0}^{N-1}\widetilde{x}(n)e^{-j\frac{2\pi}{N}nk}=\sum_{n=0}^{N-1}\widetilde{x}(n)W_N^{nk}$$
$$\widetilde{x}(n)=IDFS[\widetilde{X}(k)]=\frac{1}{N}\sum_{k=0}^{N-1}\widetilde{X}(k)e^{j\frac{2\pi}{N}nk}=\frac{1}{N}\sum_{k=0}^{N-1}\widetilde{X}(k)W_N^{-nk}$$
<table>
<tr><td>
    <td>基频序列（信号）
    <td>周期
    <td>基频
    <td>k次谐波序列
<tr><td>连续周期
    <td>$e^{j\Omega_0t}=e^{j\frac{2\pi}{T_0}t}$
    <td>$T_0$
    <td>$\Omega_0={\frac{2\pi}{T_0}}$
    <td>$e^{jk\frac{2\pi}{T_0}t}$
 <tr><td>离散周期
    <td>$e^{j\Omega_0n}=e^{j\frac{2\pi}{N}n}$
    <td>$N$
    <td>$\omega_0={\frac{2\pi}{N}}$
    <td>$e^{jk\frac{2\pi}{N}n}$
</table>
