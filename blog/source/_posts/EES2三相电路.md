---
title: EES2三相电路
date: 2023-11-03 22:55:07
tags:
- 电力系统
- 数学物理基础
categories:
- Elektrotechnik
- Elektroenergiesysteme
mathjax: true
---
[三相](https://zh.wikipedia.org/wiki/%E4%B8%89%E7%9B%B8_(%E7%94%B5%E5%AD%A6))


## 简单的三相电路
星形电路Sternschaltung
![Test](/images/Sternschaltung.png)

三个电压除以阻抗得到的电流表达式：

1. 电流$I_R$的表达式：

$$I_R(t) = \frac{V_R(t)}{Zy} = \frac{V_Rm \cdot e^{j\omega t}}{Zy}$$

2. 电流$I_S$的表达式：

$$I_S(t) = \frac{V_S(t)}{Zy} = \frac{V_Sm \cdot e^{j(\omega t + \frac{2\pi}{3})}}{Zy}$$

3. 电流$I_T$的表达式：

$$I_T(t) = \frac{V_T(t)}{Zy} = \frac{V_Tm \cdot e^{j(\omega t + \frac{4\pi}{3})}}{Zy}$$

三相电压通过阻抗产生的电流，其中$I_R$、$I_S$和$I_T$代表每个相位的电流，$V_Rm$、$V_Sm$和$V_Tm$代表它们的峰值电压
$\omega$表示角速度，$t$表示时间，$Zy$表示阻抗。

视在功率（S）可以表示为以下公式：

$S = V \cdot I^*$

当三个端口的最大电压和阻抗都相等时：

对于一个端口的视在功率可以用如下的方式表示：

$ S = \frac{V^2}{Zy} \cdot e^{j\theta}$
在这个表达式中：
- $S$ 代表视在功率，通常是一个复数。
- $V$ 代表电压的复数幅值（峰值）。
- $Zy$ 代表阻抗，也是一个复数。
- $\theta$ 代表相位差，通常以复数形式表示。

相位差 $\theta$ 是一个复数，它可以影响视在功率的实部和虚部，从而影响有功功率和无功功率的分布。
这里我们可以得出一个重要的结论，对于单个端口的视在功率是一个定值，不随时间而变化。

但是计算总视在功率不能简单的乘以3，视在功率是一个复数，遵循矢量加法的原则。
我们可以先通过将星形电路转化为三角电路分析,变化的公式放在最后。
三角电路Dreieckschaltung
![Test](/images/Dreieckschaltung.png)
端口之间的相位差是固定的，因此端口间的电压和电流可以根据端口的电流电压确定。
因此可以用端口的电流和电压表示转化后的阻抗。

每个端口的电流与电压之间的相位差是固定的，并且相位差是120度 $\frac{2\pi}{3}$弧度，那么你可以使用以下方式表示阻抗Z：
$$
Z_{\Delta} = \sqrt{3} \cdot \frac{U_{rs}}{I_r}
$$
其中，
- $Z_{\Delta}$ 代表阻抗。
- $\sqrt{3}$ 是考虑三相系统中电流和电压之间的120度相位差的常数。
- $U_{rs}$代表端口 R 和 S 之间的电压幅值（峰值）。
- $I_r$ 代表端口 R 的电流幅值（峰值）。


端口之间的电压差$U_{sr}$,$U_{rt}$,$U_{ts}$ 称为线电压，记作$U_l$, 
端口上的电流$I_s$ , $I_r$ , $I_t$ 称为线电流，记作 $I_l$.
所以这里的阻抗记作
$$
Z_{\Delta} = \frac{\sqrt{3} \cdot Ul}{Il}
$$
所以总视在功率等于这三个电阻上的视在功率的矢量和：
三相交流系统的视在功率（Apparent Power）通常由下面的公式计算：
$$
S = \sqrt{3} \cdot V_L \cdot I_L
$$
其中：
- $S$ 代表视在功率，通常以复数表示。
- $sqrt{3}$ 是一个常数，是为了考虑三相系统中电流和电压之间的120度相位差。
- $V_L$ 代表线电压（Line Voltage），也可以是相电压（Phase Voltage）的峰值。
- $I_L$ 代表线电流（Line Current），也可以是相电流（Phase Current）的峰值。



{notel default fa-info 三角电路和星形电路转化}
从三角形电路变换到Y型电路：

$$R_{ab}=\frac{R_{a}R_{b}}{R_{a}+R_{b}+R_{c}}$$
$$R_{ac}=\frac{R_{a}R_{c}}{R_{a}+R_{b}+R_{c}}$$
$$R_{bc}=\frac{R_{b}R_{c}}{R_{a}+R_{b}+R_{c}}$$

从Y型电路变换到三角形电路：

$$R_{a}=\frac{R_{ab}R_{ac}}{R_{ab}+R_{ac}+R_{bc}}$$
$$R_{b}=\frac{R_{ab}R_{bc}}{R_{ab}+R_{ac}+R_{bc}}$$
$$R_{c}=\frac{R_{ac}R_{bc}}{R_{ab}+R_{ac}+R_{bc}}$$

其中，$R_{a}$、$R_{b}$、$R_{c}$ 分别表示三角形电路中的电阻，$R_{ab}$、$R_{ac}$、$R_{bc}$ 分别表示 Y型电路中心点和 1、2、3 节点的连线上的电阻。

