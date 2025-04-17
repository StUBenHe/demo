---
title: EES3三相电路的数学处理
date: 2023-11-07 00:55:25
tags:
- 电力系统
- 数学物理基础
- 系统转换
categories:
- Elektrotechnik
- Elektroenergiesysteme
mathjax: true
---
[电力电子坐标变换、三相对称电压形式与主控轴的关系:](https://zhuanlan.zhihu.com/p/576571778#:~:text=%E4%BB%8E%E4%B8%89%E7%9B%B8%E9%9D%99%E6%AD%A2%E5%9D%90%E6%A0%87%E7%B3%BB%EF%BC%88abc0%EF%BC%89%E5%8F%98%E6%8D%A2%E5%88%B0%E4%B8%A4%E7%9B%B8%E9%9D%99%E6%AD%A2%E5%9D%90%E6%A0%87%E7%B3%BB%EF%BC%88%20%CE%B1%CE%B2,0%EF%BC%89%E7%9A%84%E5%9D%90%E6%A0%87%E5%8F%98%E6%8D%A2abc%E2%86%92%20%CE%B1%CE%B2%20%E7%A7%B0%E4%B8%BAclark%E5%8F%98%E6%8D%A2%E3%80%82)


## 一般三相电路的转化

C.L. Fortescue 提出所有的不对称三相交流系统unsymmetrisches Drehstromsystem可以拆分成三个堆成的电压系统
这三个分别是
|名称          | Index | 描述 |
|--------------|-----|-----|
| Mitsystem    | 1   | 与原系统RST同向转动 RST  |
| Gegensystem  | 2   | 与原系统RST相反转动 TSR   |
| Nullsystem   | 0   | 固定方向的电压系统   |

![Test](/images/Drehstromsystem.png)

Mitsystem 和 Gegensystem由于对称性，只需要一个最大值和相位角α就可以表示。
$\alpha = e^{j2/ 3\pi}$

因此这些对称系统只要求出相对应的最大值就可以

经过数学计算，可以得到如下转换公式：
以下是您描述的方程式使用MathJax表示的方式：

$$
U_{RST} = C_{120} U_{120}
$$
其中$C_{120}=$

$$
\begin{Bmatrix}
1 & 1 & 1  \\ 
α² & α & 1 \\
α & α² & 1
\end{Bmatrix}
$$
逆变换如下：

$$U_{120} = (C_{120})^{-1} \cdot U_{RST}$$
其中$(C_{120})^{-1}=$
$$
\frac{1}{3} \cdot
\begin{bmatrix}
1 & α & α² \\
1 & α² & α \\
1 & 1 & 1
\end{bmatrix}
$$

## αβ0-Komponenten und dq0-Transformation
将三个电压矢量相加，最后得到一个矢量，这个矢量落在垂直坐标系中的数

α和β是指两个相互垂直的轴，将原电流系统转化为正交的量，这就使得旋转的电流系统变成了旋转的轴与坐标，这种旋转的坐标称之为dq0-Transformation
本质上利用了数学上投影的原理
### αβ0-Komponenten
计算过程以放入文章开头连接

1,
$$U_{RST} = (C_{αβ0})\cdot U_{αβ0}$$
其中$C_{αβ0}=$
$$
\frac{1}{2} \cdot
\begin{bmatrix}
  2 & 0 & 2 \\
  -1 & \sqrt{3} & 2 \\
  -1 & -\sqrt{3} & 2
\end{bmatrix}
$$
2,
$$U_{αβ0} = (C_{αβ0})^{-1} \cdot U_{RST}$$
其中$(C_{αβ0})^{-1}=$
$$
\frac{1}{3} \cdot
\begin{bmatrix}
2 & -1 & -1 \\
0 & \sqrt{3} & -\sqrt{3} \\
1 & 1 & 1
\end{bmatrix}
$$
3,
$$
U_{\alpha\beta0} = (C_{\alpha\beta0})^{-1} \cdot U_{RST} = (C_{\alpha\beta0})^{-1} \cdot (C_{120}) \cdot U_{120} 
$$
其转换矩阵为：
$$
\begin{bmatrix}
1 & 1 & 0 \\
-j & j & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

### dq0-Transformation
这种变换的本质是将坐标轴旋转起来，
Clark变换和Park变换是在电力电子、电机控制和电力系统中广泛使用的数学变换技术，用于将三相交流电压或电流变换为两相（dq坐标）的电压或电流，以简化分析和控制。这些变换通常用于交流电机驱动、电力系统稳定性分析和控制等领域。以下是对Clark变换和Park变换的简要解释：
$\theta$ 为初始相位

$$
     \begin{align*}
     d &= \alpha \cos(\theta) + \beta \sin(\theta) \\
     q &= -\alpha \sin(\theta) + \beta \cos(\theta)
     \end{align*}
$$
其中，α和β是αβ坐标下的信号，θ是旋转角度。
我们就可以得到如下变换方程

$$U_{dp0} = (C_{αβ0-dp0})^{-1} \cdot U_{αβ0}$$

$$
\begin{pmatrix}U_d  \\ U_q \\ U_0\end{pmatrix}=\begin{pmatrix}\cos\theta    & \sin\theta   &0 \\
 -\sin\theta    & \cos\theta   &0 \\  0&0 &1\end{pmatrix}\cdot \begin{pmatrix}U _\alpha \\ U_\beta \\ U_0\end{pmatrix}
$$

相反的
$$C_{αβ0-dp0}(-\theta)=$$

$$
\frac{1}{3} \cdot
\begin{bmatrix}
\cos(-\theta) & -\sin(-\theta) & 0   \\
\sin(-\theta) & \cos(-\theta) & 0   \\
0 & 0 & 1
\end{bmatrix}
$$

## 三种系统下的功率计算

$ S = U_R \cdot I_R^* + U_S \cdot I_S^* + U_T \cdot I_T^* $

$ S_{120} = 3 \cdot U_1 \cdot I_1^* + U_2 \cdot I_2^* + U_0 \cdot I_0^* $

$$
S_{\alpha\beta0} = \frac{3}{2} \cdot \left(U_\alpha \cdot I_\alpha^* + U_\beta \cdot I_\beta^* \right) + 3 \cdot U_0 \cdot I_0^* 
$$

$ S_{dq0} = \frac{3}{2} \cdot \left(U_d \cdot I_d^* + U_q \cdot I_q^* \right) + 3 \cdot U_0 \cdot I_0^* $


## Komponententransformation的应用
- 计算不平衡的电源
- 分析电机
- 控制变频器
### 用于相位同步的锁相环PLL
### 控制电池充电电流转换器


