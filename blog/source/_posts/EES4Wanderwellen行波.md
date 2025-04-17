---
title: EES4Wanderwellen行波
date: 2023-11-10 01:36:08
tags:
- 电力系统
- 数学物理基础
- 传输线理论
- 行波
categories:
- Elektrotechnik
- Elektroenergiesysteme
mathjax: true
---
[传输线理论](https://zh.wikipedia.org/wiki/%E4%BC%A0%E8%BE%93%E7%BA%BF)

## 一般传导方程

由于常温超导技术并不成熟，现实生活中人们所用的导体都不是理想里。
为了更好地分析电在导体中的情况，我们将抽象模拟一个复阻抗Z和复导纳Y
复阻抗（Z）和复导纳（Y）是在交流电路分析中使用的概念。它们与电阻、电抗、导纳和导抗等参数有关。以下是它们的定义：

复阻抗（Z）komplexen Impedanz:
   $ Z = R + j\omega \cdot  L $

复导纳（Y）komplexen Admittanz:
   $ Y = G + j\omega \cdot C $
 - Widerstandsbelag R
 - Induktivitätsbelag L
 - Kapazitätsbelag C
 - Ableitungsbelag G

 ![Test](/images/Wanderwellen.png)

 dU和dI分别是可以理解为电压和电流在导线上的微分
 因此可以得出两个公式：
- $U+\mathrm{d} U= Z\mathrm{d} x\cdot (I+\mathrm{d} I)+U$
- $I+\mathrm{d} I= Y\mathrm{d} x\cdot \mathrm{d} U+I$
由于ZIdx >> ZdIdx，可以化简:

- $\frac{\mathrm{d} U}{\mathrm{d} x}=Z\cdot I$
- $\frac{\mathrm{d} I}{\mathrm{d} x}=Y\cdot U$

二阶导:
- $\frac{\mathrm{d}^{2}  I}{\mathrm{d} x^{2}}-Z\cdot Y\cdot I=0  $
- $\frac{\mathrm{d}^{2}  U}{\mathrm{d} x^{2}}-Z\cdot Y\cdot U=0  $

在导体上电压与位置的关系可以表示为：
$ U\left ( x \right ) =A\cdot e^{\gamma x} +B\cdot e^{-\gamma x} $

在导体上电流与位置的关系可以表示为：
$ I\left ( x \right ) =C\cdot e^{\gamma x} +D\cdot e^{-\gamma x} $
$ =I\left ( x \right ) =  \frac{1}{Z_w} (A\cdot e^{\gamma x} +B\cdot e^{-\gamma x}) $


Übertragungskonstante: $ \gamma =\sqrt{YZ} $
Wellenwiderstand: $ Z_w=\sqrt{\frac{Z}{Y} } $

*** 对于无损导线 Verlustfreie Leitung R=0 G=0 ***

## Leitungstheorie 传导线理论
根据基尔霍夫定律可以得出以下无损电路的偏微分方程
$$
\frac{\partial ^{2}u }{\partial x^{2} } - LC\cdot \frac{\partial^{2}  u}{\partial t^{2} }=0
$$
$$
\frac{\partial ^{2}i }{\partial x^{2} } - LC\cdot \frac{\partial^{2}  i}{\partial t^{2} }=0
$$
这个方程的解就是行波方程：
$$
u\left ( x,t \right )  = u_v\left ( x-v\cdot t \right ) +u_r\left ( x+v\cdot t \right )
$$
$$
i\left ( x,t \right )  = \frac{1}{Z} [u_v\left ( x-v\cdot t \right ) -u_r\left ( x+v\cdot t \right )]=i_v(x-v\cdot t)+i_r(x+v\cdot t)
$$
其中 v正向波，r表示反射波。这种波在电流和电压的计算中是满足叠加定理的。

 ![Test](/images/Leitungsverzweigung.png)

$$
\frac{u_{v1} }{Z_{1}} -\frac{u_{r1}}{Z_1}=\frac{u_{v2}}{Z_2} +\frac{u_{v2}}{Z_3}
$$

### Wellengitter nach Bewley

 $$A(p)=\frac{Z_0-Z_L}{Z_0+Z_L}   $$
 $$ B(p)=\frac{Z_A-Z_L}{Z_A+Z_L} $$   
 $$A(p)=2\cdot\frac{Z_A}{Z_A+Z_L} $$  
 
 $$
 U_L (p)=X(p)\cdot U_0(p)\cdot C(p)\cdot \frac{1}{1-A(p)\cdot B(p)e^{-2pt} } 
 $$

 $$
 =U_0(p)\cdot H(p)
 $$
 Übertragungsfunktion:
 $$
 H(p)=\frac{X(p)\cdot C(p)}{1-A(p)\cdot B(p)e^{-pt} } 
 $$
 ![Test](/images/Wellengitter.png)