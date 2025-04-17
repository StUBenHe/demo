---
title: 麦克斯韦方程组推导
date: 2023-12-05 20:01:41
tags:
- 麦克斯韦方程组
- 电磁波
categories:
- 数学物理基础
- 微分方程
mathjax: true
---

[麦克斯韦求光速](https://www.zhihu.com/tardis/zm/art/81867668?source_id=1005)

## 麦克斯韦方程组 Die Maxwellschen Gleichungen

*   高斯电场定律：描述电场由电荷产生。
*   高斯磁场定律：描述磁场由磁偶极子产生。
*   法拉第电磁定律：描述时变磁场产生电场的过程。
*   麦克斯韦-安培定律：描述电场产生磁场的过程，时变电场或电流产生磁场。


|名称| 积分公式    |微分公式   |
|---------------------|----------|---------
|**高斯电场定律**| $\\oint\_S \\mathbf{E} \\cdot d\\mathbf{A} = \\frac{Q}{\\varepsilon\_0}$ | $\nabla \\cdot \\mathbf{E} = \\frac{\\rho}{\\varepsilon\_0}$    |
|**高斯磁场定律**| $\\oint\_S \\mathbf{B} \\cdot d\\mathbf{A} = 0$ |$\\nabla \\cdot \\mathbf{B} = 0$  |
|**法拉第电磁感应定律**|$\\oint\_C \\mathbf{E} \\cdot d\\mathbf{l} = -\\frac{d}{dt} \\iint\_S \\mathbf{B} \\cdot d\\mathbf{A}$ | $\\nabla \\times \\mathbf{E} = -\\frac{\\partial\\mathbf{B}}{\\partial t}$|
|**麦克斯韦-安培定律**| $\\oint\_C \\mathbf{B} \\cdot d\\mathbf{l} = \\mu\_0 \\iint\_S \\mathbf{J} \\cdot d\\mathbf{A} + \\mu\_{0} I$  | $\\nabla \\times \\mathbf{B} = \\mu\_0 \\mathbf{J} + \\mu\_0\\varepsilon\_0 \\frac{\\partial \\mathbf{E}}{\\partial t}$|

## 麦克斯韦方程组（积分形式）推导


麦克斯韦在基于对现有理论整合前三个表达式。受到法拉第电磁感应定律的启发，他创造性的提出变化的电场生成磁场，用于补充原来的安培定律。

也就是说这四个公式都是描述已有的结论，将文字理论转换为数学语言。

首先我们需要认识_通量_：穿过某个面的某个东西的量。 所谓的_电通量_也就是闯过曲面的电场线的量。
举个例子，当我们想知道自来水管水的通量，我们可以简单的通过水流的速度*横截面  ，既 $\\mathbf{v}$\*S
借助这个模型，认识麦克斯韦方程组

### 高斯电场定律 Gauss’s Gesetz

描述：通过一个_封闭曲面_的_电场强度_的_面积积分_等于该曲面内部的_总电荷量_除以_真空中的电场常数_。

在上述公式中，当此时的截面是一个曲面时，我们利用微积分的思想来处理，既用$\\oint\_S$ 表示封闭的曲面积分，用dA表示曲面微分。 由于电场线是描述电场强度的线，因此电场强度可以看作这里的水流。因此我们就得到了高斯电场定律积分表达式：

$\\oint\_S \\mathbf{E} \\cdot d\\mathbf{A} = \\frac{Q}{\\varepsilon\_0}$

其中，符号代表以下物理量：

*   $\\oint\_S$ 表示对一个封闭曲面 S 的面积积分，该曲面可以任意形状。
*   $\\mathbf{E}$ 代表电场强度矢量，表示在观察点上的电场。
*   $d\\mathbf{A}$ 是曲面 S 上的微小面积元素，指向曲面的外法线。
*   $Q$ 代表曲面内包围的总电荷量。
*   $\\varepsilon\_0$ 代表真空中的电场常数（也称为真空介电常数）。

### 高斯磁定律-Gaussches-Gesetz-fur-Magnetfelder

既然电荷数量可以用电场强度的面积分表示，那么磁场强度的面积分可不可以也用来表示磁呢？  
答案是否定的，因为目前来看世界上并不单独存在某个磁极。也就是说所有的磁场都是从N级出发，到S截至。因此高斯磁定律描述到：

_磁感应强度 $\\mathbf{B}$ 通过任意封闭曲面 $S$ 的面积积分等于零。_

$\\oint\_S \\mathbf{B} \\cdot d\\mathbf{A} = 0$

### 法拉第电磁感应定律-Induktionsgesetz 

简单来说，法拉第电磁感应定律描述的就是，变化的磁场产生电流。

所谓变化的磁场，就是说磁场强度 $\\mathbf{B}$随位置$x$ 和时间$t$ 而变化。由于位置变化往往可以通过时间描述，所以我们可以通过对时间求导，来描述变化的磁场。

既电动势 $\\varepsilon =$  
$-\\frac{d}{dt} \\iint\_S \\mathbf{B} \\cdot d\\mathbf{A}$

另一方面电流的来源是电动势，我们可以通过电场强度环流（当带电体在静电场中移动时，静电场力对带电体要作功。）来表示：

$\\varepsilon q =\\oint\_C \\mathbf{E}q \\cdot d\\mathbf{l}$

去掉点电荷q，电动势可以表示为：

$\\varepsilon =\\oint\_C \\mathbf{E} \\cdot d\\mathbf{l}$

综合起来，结合法拉第电磁感性定律的描述：

一个封闭回路 $C$ 上的电动势（电压）等于磁感应强度 $\\mathbf{B}$ 通过该回路的磁通量的变化率。这个定律可以表示为：

$\\oint\_C \\mathbf{E} \\cdot d\\mathbf{l} = -\\frac{d}{dt} \\iint\_S \\mathbf{B} \\cdot d\\mathbf{A}$

其中，

*   $\\oint\_C$ 表示对封闭回路
*   $\\mathbf{E}$ 代表电场强度，
*   $d\\mathbf{l}$ 是回路上的微小路径元素，
*   $\\iint\_S$ 表示对一个封闭曲面
*   $S$ 的面积积分，
*   $\\mathbf{B}$ 代表磁感应强度，
*   $d\\mathbf{A}$ 是曲面
*   $S$ 上的微小面积元素，
*   $d/dt$ 表示对时间的导数。
*   $-$ 楞次定律

\*楞次定律：变化的磁通量感生出来的电场能再次激发出来的磁场，这个磁场会限制原有磁场的变化。

### 麦克斯韦-安培定律-Amperesches-Gesetz

安培环路定律表明，在真空中，载有稳定电流的导线所产生的磁场与环绕导线的任意闭合回路（环路）上的磁场积分之间存在关系。

$$  
\\oint\_{\\mathbf{C}} \\mathbf{B} \\cdot \\mathrm{d}\\mathbf{l} = \\mu\_0 I  
$$  
其中，

*   $\\oint\_{\\mathbb{C}}$ 表示沿着闭合回路 $\\mathbf{C}$ 的路径积分。
*   $\\mathbf{B}$ 是磁感应强度（B场）。
*   $d\\mathbf{l}$ 是微小线元素向量。
*   $\\mu\_0$ 是磁常数。
*   $I$ 是闭合回路 $\\mathbf{C}$ 所围住的电流。

为了满足与磁生电的对称性，麦克斯韦提出变化的电场也能产生磁场

$$  
\\oint\_C \\mathbf{B} \\cdot d\\mathbf{l} = \\mu\_0 \\iint\_S \\mathbf{J} \\cdot d\\mathbf{A}  
$$

其中，

*   $\\oint\_C$ 表示对封闭回路
*   $C$ 的环路积分
*   $\\mathbf{B}$ 代表磁感应强度
*   $d\\mathbf{l}$是回路上的微小路径元素
*   $\\mu\_0$ 代表真空磁导率
*   $\\iint\_S$ 表示对封闭曲面
*   $S$ 的面积积分，
*   $\\mathbf{J}$ 代表电流密度
*   $d\\mathbf{A}$ 是曲面
*   $S$ 上的微小面积元素

将二者综合  
$$  
\\oint\_C \\mathbf{B} \\cdot d\\mathbf{l} = \\mu\_0 \\iint\_S \\mathbf{J} \\cdot d\\mathbf{A} + \\mu\_{0} I  
$$

##麦克斯韦方程组（微分形式）推导 "麦克斯韦方程组（微分形式）推导")麦克斯韦方程组（微分形式）推导


## 麦克斯韦方程组（微分形式）推到

### 斯托克斯公式（Stokes’-Theorem）:

斯托克斯公式描述了一个曲面上的环绕一条曲线的矢量场的环绕积分与通过这个曲面的矢量场的通量之间的关系。数学上表达如下：

如果 $S$ 是一个有向分段光滑曲面，且 $C$ 是 $S$ 的边界曲线，$F$ 是定义在 $S$ 上的一个矢量场，那么斯托克斯公式为：

$$  
\\oint\_C \\mathbf{F} \\cdot d\\mathbf{r} = \\iint\_S \\nabla \\times \\mathbf{F} \\cdot d\\mathbf{S}  
$$

其中，

*   $\\oint\_C$表示沿曲线 (C) 的环绕积分。
*   $\\iint\_S$ 表示对曲面 (S) 的面积分。
*   $\\mathbf{F}$ 是矢量场。
*   $d\\mathbf{r}$ 是曲线元素向量。
*   $\\nabla \\times \\mathbf{F}$ 是矢量场 $\\mathbf{F}$的旋度。
*   $d\\mathbf{S}$ 是曲面元素向量。

### 高斯散度定理（Gauss’-Divergence-Theorem）：

高斯散度定理描述了一个闭合曲面内的矢量场的散度与通过这个闭合曲面的通量之间的关系。数学上表达如下：

如果 $V$ 是一个有向分段光滑的闭合曲面，$E$ 是 $V$ 的内部区域，且 $F$ 是定义在 $V$ 上的一个矢量场，那么高斯散度定理为：

$$ \\oiint\_V \\mathbf{F} \\cdot d\\mathbf{S} = \\iiint\_E \\nabla \\cdot \\mathbf{F} , dV$$

其中，

*   $\\oiint\_V$ 表示对闭合曲面 $V$ 的通量积分。
*   $\\iiint\_E$ 表示对区域 $E$ 的体积积分。
*   $\\mathbf{F}$ 是矢量场。
*   $d\\mathbf{S}$ 是闭合曲面元素向量。
*   $\\nabla \\cdot \\mathbf{F}$ 是矢量场 $\\mathbf{F}$ 的散度。
*   $dV$ 是体积元素。

### 麦克斯韦方程的微分形式： "麦克斯韦方程的微分形式：")麦克斯韦方程的微分形式：

通过斯托克斯公式和高斯散度定理，可以从麦克斯韦方程的积分形式得到微分形式。以下是麦克斯韦方程的微分形式：

**麦克斯韦方程 - 电场的散度定律：**  
$$  
\\nabla \\cdot \\mathbf{E} = \\frac{\\rho}{\\varepsilon\_0}  
$$

**麦克斯韦方程 - 磁场的散度为零：**  
$$  
\\nabla \\cdot \\mathbf{B} = 0  
$$

**麦克斯韦方程 - 电场的旋度定律：**  
$$  
\\nabla \\times \\mathbf{E} = -\\frac{\\partial \\mathbf{B}}{\\partial t}  
$$

**麦克斯韦方程 - 磁场的旋度定律（安培环路定律）：**  
$$  
\\nabla \\times \\mathbf{B} = \\mu\_0 \\mathbf{J} + \\mu\_0\\varepsilon\_0 \\frac{\\partial \\mathbf{E}}{\\partial t}  
$$

[](#麦克斯韦计算电磁波的速度 "麦克斯韦计算电磁波的速度")麦克斯韦计算电磁波的速度
--------------------------------------------

首先我们线给出麦克斯韦方程组的微分表达式  
$$  
\\nabla \\cdot \\mathbf{E} = \\frac{\\rho}{\\varepsilon\_0}  
$$

$$  
\\nabla \\cdot \\mathbf{B} = 0  
$$

$$  
\\nabla \\times \\mathbf{E} = -\\frac{\\partial \\mathbf{B}}{\\partial t}  
$$

$$  
\\nabla \\times \\mathbf{B} = \\mu\_0 \\mathbf{J} + \\mu\_0\\varepsilon\_0 \\frac{\\partial \\mathbf{E}}{\\partial t}  
$$

对 $\\nabla \\times \\mathbf{E}$再求一次旋度  
$$  
\\nabla \\times \\nabla \\times \\mathbf{E}  
\=\\nabla \\times (\\nabla \\times \\mathbf{E}) = \\nabla (\\nabla \\cdot \\mathbf{E}) - \\nabla^2 \\mathbf{E}=-\\frac{\\partial \\nabla \\times\\mathbf{B}}{\\partial t}  
$$  
在真空，$\\rho=0$ ; $\\mathbf{J} =0$

所以这个式子可以简化为  
$$  
\\nabla^2 \\mathbf{E}=\\mu\_0\\varepsilon\_0\\frac{\\partial ^2\\mathbf{E}}{\\partial t^2}  
$$

通过矢量微分运算，我们可以将 $\\nabla \\times \\nabla \\times \\mathbf{E}$ 与波动方程联系起来。首先，波动方程通常表示为：

$$  
\\frac{\\partial^2 \\mathbf{E}}{\\partial t^2} = v^2 \\nabla^2 \\mathbf{E}  
$$

对于电场矢量 $\\mathbf{E} = (E\_x, E\_y, E\_z)$，我们可以将上述表达式应用到每个分量上：

$$  
(\\nabla \\times \\nabla \\times \\mathbf{E})\_x = \\nabla (\\nabla \\cdot \\mathbf{E})\_x - \\nabla^2 E\_x  
$$

$$  
(\\nabla \\times \\nabla \\times \\mathbf{E})\_y = \\nabla (\\nabla \\cdot \\mathbf{E})\_y - \\nabla^2 E\_y  
$$

$$  
(\\nabla \\times \\nabla \\times \\mathbf{E})\_z = \\nabla (\\nabla \\cdot \\mathbf{E})\_z - \\nabla^2 E\_z  
$$

将这些结果代入波动方程，我们可以观察到一些特殊的关系：

$$  
\\frac{\\partial^2 \\mathbf{E}}{\\partial t^2} = c^2 \\nabla^2 \\mathbf{E} \\implies \\frac{\\partial^2 \\mathbf{E}}{\\partial t^2} - c^2 \\nabla^2 \\mathbf{E} = 0  
$$

这表明，如果电场矢量满足波动方程，那么 $\\nabla \\times \\nabla \\times \\mathbf{E}$ 将等于零。这是电磁场在真空中的波动方程，描述了电磁波在真空中传播的行为。

类似于电场的情况，我们可以考虑磁场的旋度的旋度 $\\nabla \\times \\nabla \\times \\mathbf{B}$。根据矢量微分运算，磁场的旋度的旋度表达式为：

$$  
\\nabla \\times \\nabla \\times \\mathbf{B} = \\nabla (\\nabla \\cdot \\mathbf{B}) - \\nabla^2 \\mathbf{B}  
$$

对于磁场，我们有 $\\nabla \\cdot \\mathbf{B} = 0$，因为磁场不存在磁荷。因此，上述表达式简化为：

$$  
\\nabla \\times \\nabla \\times \\mathbf{B} = -\\nabla^2 \\mathbf{B}  
$$

将这个表达式代入磁场的波动方程，我们得到：

$$  
\\frac{\\partial^2 \\mathbf{B}}{\\partial t^2} = c^2 \\nabla^2 \\mathbf{B} \\implies \\frac{\\partial^2 \\mathbf{B}}{\\partial t^2} + c^2 \\nabla^2 \\mathbf{B} = 0  
$$

这是描述磁场在真空中传播的波动方程。与电场类似，这个方程说明磁场也可以以波的形式在真空中传播。  
$$  
\\nabla^{2} f=\\frac{1}{v^{2} } \\frac{\\partial^2}{\\partial t^{2}}f  
$$

这样我们可以得到电磁是以波的形式传递，并且速度是  
$$  
v=\\frac{1}{\\sqrt{\\mu\_0\\varepsilon\_0}}=3\\cdot10^{8} m/s  
$$  
当时麦克斯韦猜测光的本质是电磁波。

[](#波函数 "波函数")波函数
-----------------

电磁波在一维情况下，可以用标量电场 $E$ 或矢量电场 $\\mathbf{E}$来描述。为了简化，我们考虑电场 $E$ 在 X 轴上的波函数。

假设电场 $E$ 关于 X 轴的波函数为$E\_x(x, t)$。电磁波的波动方程为：

$$  
\\frac{\\partial^2 E\_x}{\\partial t^2} = c^2 \\frac{\\partial^2 E\_x}{\\partial x^2}  
$$

电场 $E\_x$ 可以写成形式 $E\_x(x, t) = A \\cos(kx - \\omega t + \\phi)$，其中：

*   A 是振幅，
*   k 是波数，
*   $\\omega$ 是角频率，
*   $\\phi$ 是相位。

假设电磁波在 X 轴上的波函数可以写成发出波 $E\_{x+}$ 和回波 $E\_{x-}$ 的形式，可以表示为：

$ E\_x(x, t) = E\_{x+}(x - ct) + E\_{x-}(x + ct) $

其中：

*   $E\_{x+}(x - ct)$ 是沿正 X 方向传播的前进波，
*   $E\_{x-}(x + ct)$ 是沿负 X 方向传播的回波。

这样的形式是为了考虑波在正方向和负方向的传播，同时保持波动方程的形式。在这个表达式中，波数 $k$ 和角频率 $\\omega$ 都包含在 $E\_{x+}$和 $E\_{x-}$ 中

我们可以通过将电场 $E\_x$ 的波函数 $E\_x(x, t) = E\_{x+}(x - ct) + E\_{x-}(x + ct)$ 代入波动方程 $\\frac{\\partial^2 E\_x}{\\partial t^2} = c^2 \\frac{\\partial^2 E\_x}{\\partial x^2}$ 中，来验证这个波函数满足波动方程。

首先，我们计算波函数 $E\_x$ 关于时间的二阶偏导数：

$$  
\\frac{\\partial^2 E\_x}{\\partial t^2} = -c^2 E\_{x+}’’(x - ct) + c^2 E\_{x-}’’(x + ct)  
$$

其中，$E\_{x+}’’$ 和 $E\_{x-}’’$ 分别表示 $E\_{x+}$ 和 $E\_{x-}$ 关于 x 的二阶导数。

然后，计算波函数 $E\_x$ 关于空间的二阶偏导数：

$$  
\\frac{\\partial^2 E\_x}{\\partial x^2} = E\_{x+}’’(x - ct) + E\_{x-}’’(x + ct)  
$$

将这两个结果代入波动方程 $\\frac{\\partial^2 E\_x}{\\partial t^2} = c^2 \\frac{\\partial^2 E\_x}{\\partial x^2}$ 中，我们得到：

$$  
\-c^2 E\_{x+}’’(x - ct) + c^2 E\_{x-}’’(x + ct) = c^2 E\_{x+}’’(x - ct) + c^2 E\_{x-}’’(x + ct)  
$$

通过整理，我们可以看到这个等式成立，所以波函数$E\_x(x, t) = E\_{x+}(x - ct) + E\_{x-}(x + ct)$ 是电磁波的波动方程的解。这个表达式描述了沿正方向和负方向传播的波。