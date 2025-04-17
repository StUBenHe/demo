---
title: EES1交流电系统
date: 2023-11-02 19:15:39
tags:
- 电力系统
- 数学物理基础
- 单相交流系统
- 三相交流系统
categories:
- Elektrotechnik
- Elektroenergiesysteme
mathjax: true
---


[交流电系统] (https://de.wikipedia.org/wiki/Wechselstrom)
[三相交流系统] (https://de.wikipedia.org/wiki/Dreiphasenwechselstrom)


## 单相交流系统 Einphasiges Wechselstromsystem

单相交流系统是一种交流电力系统，它由单一的交流电源（通常是单一的交流电压源）供电。在单相交流系统中，电流和电压是单一的正弦波，并且它们具有相同的频率和周期。

单相交流系统通常用于小型家庭电力供应、小型工业设备以及轻型商业用途。在家庭中，我们通常使用单相交流系统来供电，它通常以110V或220V的电压供应电器和灯具。

与之相对的是三相交流系统，它由三个相互位移120度的交流电源组成，通常用于大型工业设备、工厂和电力分配系统，因为它具有更高的功率容量和更平稳的功率供应。

总之，单相交流系统是一种电力系统，其中只有一个交流电源，用于满足较小电力需求的应用。


基础的数学表示通常使用欧拉公式来表示瞬时电压和电流。欧拉公式可以表示正弦波形。

欧拉公式如下：

$$
e^{j\theta} = \cos(\theta) + j\sin(\theta)
$$

其中，$j$ 是虚数单位（在电学中通常用 $j$ 表示），$\theta$ 是相位角度。

对于瞬时电压 $V(t)$ 和电流 $I(t)$ 在Einphasiges Wechselstromsystem中，可以使用欧拉公式来表示：

$$
V(t) = V_{\text{max}} \cdot e^{j\omega t}
$$

$$
I(t) = I_{\text{max}} \cdot e^{j(\omega t + \phi)}
$$

其中：
- $V_{\text{max}}$ 代表电压的峰值（幅值Amplitude）。
- $I_{\text{max}}$ 代表电流的峰值（幅值）。
- $\omega$ 是角频率。
- $\phi$ 是相位差。

视在功率（scheinleistung）的公式可以通过电压和电流的有效值（均方根值）来表示。视在功率通常用 $S$ 表示，其计算公式如下：

$$
S = V_{\text{eff}} \cdot I_{\text{eff}}
$$

其中：
- $V_{\text{eff}}$代表电压的有效值Effektivwert。
- $I_{\text{eff}}$代表电流的有效值。

通过欧拉公式和有效值，你可以计算Einphasiges Wechselstromsystem中的电压、电流和视在功率。请注意，视在功率是电路中的复功率，它包括有用功率Wirkleistung和无功功率Blindleistung，通常以 VA（伏安）为单位表示。有用功率可以通过实功率（Watt，瓦特）来表示。


## 电功率基本公式 1p

首先，我们有电功率的基本公式：

$$
P(t) = V(t) \cdot I(t)
$$

其中，
- $P(t)$ 代表时间 $t$ 时刻的瞬时有用功率。
- $V(t)$ 代表时间 $t$ 时刻的电压。
- $I(t)$ 代表时间 
电压和电流通常是正弦波，可以表示为：

$$
V(t) = V_{\text{max}} \cdot \cos(\omega t)
$$

$$
I(t) = I_{\text{max}} \cdot \cos(\omega t + \phi)
$$

其中，
- $V_{\text{max}}$ 代表电压的峰值。
- $I_{\text{max}}$ 代表电流的峰值。
- $\omega$ 代表角频率。
- $\phi$ 代表相位差。

利用公式：
$$
cos(A) * cos(B) = \frac{1}{2} * [cos(A + B) + cos(A - B)]
$$

将上述电压和电流的表达式代入功率公式，得到：

$$
P(t) = \frac{1}{2} \cdot V_{\text{max}} \cdot I_{\text{max}} \cdot [\cos(2\omega t + \phi) + \cos(\phi)]
$$

$$
P(t) = V_{\text{eff}} \cdot I_{\text{eff}} \cdot [\cos(2\omega t + \phi) + \cos(\phi)]
$$


---

## 三相交流系统 Drehstromsystem

![Test](/images/1.png)

R相电压：
$$
V_R(t) = V_R \cdot e^{j\omega t}
$$

S相电压：

$$
V_S(t) = V_S \cdot e^{j(\omega t - \frac{2\pi}{3})}
$$

T相电压：
$$
V_T(t) = V_T \cdot e^{j(\omega t + \frac{2\pi}{3})}
$$
其中，$V_R$、$V_S$和$V_T$ 分别代表R相、S相和T相电压的峰值。这些表达式表示了三相交流系统中的三个电压波形，每个波形的峰值分别用相应的标记表示。
![Test](/images/2.png)


当三相电压的峰值相等时，我们可以进一步计算各相之间的电压差。
假设$V_R=V_S=V_T=V_Y$
以下是再次计算的结果：

![Test](/images/4.png)

1.（R相和S相电压之差）：

$V_{RS}(t) = V_R(t) - V_S(t)$

$V_{RS}(t) = (V_{\text{max}} \cdot e^{j\omega t}) - (V_{\text{max}} \cdot e^{j(\omega t - \frac{2\pi}{3})})$
$V_{RS}(t) = V_{\text{max}} \cdot \left(e^{j\omega t} - e^{j\omega t} \cdot e^{-j\frac{2\pi}{3}}\right)$
$V_{RS}(t) = V_{\text{max}} \cdot \left(1 - e^{-j\frac{2\pi}{3}}\right) \cdot e^{j\omega t}$


2.（R相和T相电压之差）：

$V_{RT}(t) = V_R(t) - V_T(t)$
$V_{RT}(t) = (V_{\text{max}} \cdot e^{j\omega t}) - (V_{\text{max}} \cdot e^{j(\omega t + \frac{2\pi}{3})})$
$V_{RT}(t) = V_{\text{max}} \cdot \left(e^{j\omega t} - e^{j\omega t} \cdot e^{j\frac{2\pi}{3}}\right)$
$V_{RT}(t) = V_{\text{max}} \cdot \left(1 - e^{j\frac{2\pi}{3}}\right) \cdot e^{j\omega t}$

3.（S相和T相电压之差）：

$V_{ST}(t) = V_S(t) - V_T(t)$
$V_{ST}(t) = (V_{\text{max}} \cdot e^{j(\omega t - \frac{2\pi}{3})}) - (V_{\text{max}} \cdot e^{j(\omega t + \frac{2\pi}{3})})$
$V_{ST}(t) = V_{\text{max}} \cdot \left(e^{j\omega t} \cdot e^{-j\frac{2\pi}{3}} - e^{j\omega t} \cdot e^{j\frac{2\pi}{3}}\right)$
$V_{ST}(t) = V_{\text{max}} \cdot \left(e^{-j\frac{2\pi}{3}} - e^{j\frac{2\pi}{3}}\right) \cdot e^{j\omega t}$


当三相电压的峰值相等，我们可以进行相位旋转操作，从而得到：
![Test](/images/3.png)


$V_RS(t) = V_{\text{max}} \cdot e^{j\omega t}$

$V_ST(t) = V_{\text{max}} \cdot e^{j(\omega t - \frac{2\pi}{3})}$

$V_TR(t) = V_{\text{max}} \cdot e^{j(\omega t + \frac{2\pi}{3})}$

## 电功率的基本公式 3p

如果电流和电压之间的相位差为 ϕ，而三个端口之间的相位差为 120 度，那么你可以使用相位差 ϕ 和角速度 ωt 来表示每个端口的有用功率。有用功率可以使用下面的公式来表示：

1. 对于端口 R：
$$
P_R(t) = V_{\text{eff}} \cdot I_{\text{eff}} \cdot \cos(\omega t - \phi)
$$
2. 对于端口 S：
$$
P_S(t) = V_{\text{eff}} \cdot I_{\text{eff}} \cdot \cos(\omega t - \phi - \frac{2\pi}{3})
$$
3. 对于端口 T：
$$
P_T(t) = V_{\text{eff}} \cdot I_{\text{eff}} \cdot \cos(\omega t - \phi + \frac{2\pi}{3})
$$
其中，
- $V_{\text{eff}}$ 代表电压的有效值，
- $I_{\text{eff}}$ 代表电流的有效值，
- $\omega$ 代表角速度，
- $\phi$ 代表电压和电流之间的相位差。

这些公式表示了在任何给定时间点 $t$，每个端口的有用功率，其中相位差 ϕ 和角速度 ωt 被考虑在内。

将他们加起来就得到总功率：

$$
P_{\text{total}} = \sqrt{3} \cdot V_{\text{eff}} \cdot I_{\text{eff}} \cdot \cos(\phi)
$$
这是系统的总有用功率，与时间 $t$ 无关，是一个常数值。这就证明了这个系统的稳定性。



