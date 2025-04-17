---
title: EMW01
date: 2023-11-05 20:01:41
tags:
- 麦克斯韦方程组
- 数学物理基础
categories:
- Elektrotechnik
- Elektromagnetische Wellen
mathjax: true
---

[麦克斯韦方程组](https://zh.wikipedia.org/zh-cn/%E9%A6%AC%E5%85%8B%E5%A3%AB%E5%A8%81%E6%96%B9%E7%A8%8B%E7%B5%84)

## 物理单位 Physikalische Größen

| 名称                 | Symbol   | Einheit | Alternative Bezeichnungen         |
|---------------------|----------|---------|----------------------------------|
| **magnetische Feldstärke**        | **H**    | A/m     | **H-Feld**                       |
| **elektrische Feldstärke**        | **E**    | V/m     | **E-Feld**                       |
| **Verschiebungsflussdichte** | **D** | C/m²    | -                                |
| **magnetische Flussdichte**        | **B**    | T       | **magnetische Flussdichte**      |
| **Stromdichte**      | **J**    | A/m²    | -                                |
| **Raumladungsdichte** | ρ  | C/m³    | -                                |

## 麦克斯韦方程组 Die Maxwellschen Gleichungen

- 高斯定律：描述电场由电荷产生，。
- 高斯磁定律：描述磁场由磁偶极子产生，。
- 法拉第感应定律：描述时变磁场产生电场的过程。
- 麦克斯韦-安培定律：描述电场产生磁场的过程，时变电场或电流产生磁场。

### 高斯定则 Gauss's Gesetz

#### 积分形式：
通过一个封闭曲面的电场强度的面积积分等于该曲面内部的总电荷量除以真空中的电场常数。
$\oint_S \mathbf{E} \cdot d\mathbf{A} = \frac{Q}{\varepsilon_0}$
其中，符号代表以下物理量：
- $\(\oint_S\)$ 表示对一个封闭曲面 \(S\) 的面积积分，该曲面可以任意形状。
- $\(\mathbf{E}\)$ 代表电场强度矢量，表示在观察点上的电场。
- $\(d\mathbf{A}\)$ 是曲面 \(S\) 上的微小面积元素，指向曲面的外法线。
- $\(Q\)$ 代表曲面内包围的总电荷量。
- $\(\varepsilon_0\)$ 代表真空中的电场常数（也称为真空介电常数）。
#### 微分形式：
在某一点的散度等于该点的电荷密度除以真空中的电场常数。

$\nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}$
其中，符号表示以下物理量：
- $\(\nabla \cdot \mathbf{E}\)$ 表示电场强度 $\(\mathbf{E}\)$ 的散度，即电场的发散。
- $\(\rho\)$ 代表电荷密度，表示单位体积内的电荷量。
- $\(\varepsilon_0\)$ 代表真空中的电场常数（也称为真空介电常数）。
微分形式通常用来分析电场在某一点的性质。
这表明电场强度的变化与电荷分布在该点附近的电荷密度有关。

### 高斯磁定律 Gaußsches Gesetz für Magnetfelder

#### 积分形式：
磁感应强度 $\(\mathbf{B}\)$ 通过任意封闭曲面 $\(S\)$ 的面积积分等于零：
$\oint_S \mathbf{B} \cdot d\mathbf{A} = 0$
这表明磁场没有磁单极子，没有孤立的磁荷。

#### 微分形式：

微分形式的高斯磁定律描述了磁感应强度 \(\mathbf{B}\) 的散度（发散）等于零：
$\nabla \cdot \mathbf{B} = 0$

这表明磁场的散度在空间中处处为零，表示磁场没有源头或汇点，没有磁单极子。
磁场线总是形成闭合回路。

### 法拉第电磁感应定律 Induktionsgesetz


#### 积分形式：

积分形式的法拉第电磁感应定律描述了一个封闭回路 $\(C\)$ 上的电动势（电压）等于磁感应强度 $\(\mathbf{B}\)$ 通过该回路的磁通量的变化率。这个定律可以表示为：

$\oint_C \mathbf{E} \cdot d\mathbf{l} = -\frac{d}{dt} \iint_S \mathbf{B} \cdot d\mathbf{A}$

其中，
- $\(\oint_C\)$ 表示对封闭回路 
- $\(C\)$ 的环路积分，
- $\(\mathbf{E}\)$ 代表电场强度，
- $\(d\mathbf{l}\)$ 是回路上的微小路径元素，
- $\(\iint_S\)$ 表示对一个封闭曲面 
- $\(S\)$ 的面积积分，
- $\(\mathbf{B}\)$ 代表磁感应强度，
- $\(d\mathbf{A}\)$ 是曲面 
- $\(S\)$ 上的微小面积元素，
- $\(d/dt\)$ 表示对时间的导数。

#### 微分形式：

微分形式的法拉第电磁感应定律描述了一个闭合曲线上的电场强度 $\(\mathbf{E}\)$ 等于磁感应强度 $\(\mathbf{B}\)$ 的时间导数的负值，即：
$\nabla \times \mathbf{E} = -\frac{\partial\mathbf{B}}{\partial t}$

这个表达形式强调了磁场的变化如何引起电场的环绕闭合曲线上的感应电场。

这两种形式的法拉第电磁感应定律描述了电磁感应现象，即变化的磁场会产生感应电场。积分形式描述了电动势和磁通量之间的关系，而微分形式描述了感应电场与磁场变化之间的关系。

### 安培定律 Ampèresches Gesetz

#### 积分形式：

一条封闭回路上的电流与通过该回路的磁场环路积分的关系：

$\oint_C \mathbf{B} \cdot d\mathbf{l} = \mu_0 \iint_S \mathbf{J} \cdot d\mathbf{A}$

其中，
- $\(\oint_C\)$ 表示对封闭回路
- $\(C\)$ 的环路积分
- $\(\mathbf{B}\)$ 代表磁感应强度
- $\(d\mathbf{l}\)$是回路上的微小路径元素
- $\(\mu_0\)$ 代表真空磁导率
- $\(\iint_S\)$ 表示对封闭曲面 
- $\(S\)$ 的面积积分，
- $\(\mathbf{J}\)$ 代表电流密度
- $\(d\mathbf{A}\)$ 是曲面 
- $\(S\)$ 上的微小面积元素

这个定律表明，封闭回路上的磁场环路积分等于通过回路所包围的电流总量乘以真空磁导率。它建立了电流和磁场之间的关系

 #### 微分形式：

电流密度 $\(\mathbf{J}\)$ 如何导致局部的磁场强度 $\(\mathbf{B}\)$ 变化：

$\nabla \times \mathbf{B} = \mu_0 \mathbf{J}$

其中，
- $\(\nabla \times \mathbf{B}\)$ 代表磁场强度 
- $\(\mathbf{B}\)$ 的旋度，
- $\(\mu_0\)$ 代表真空磁导率，
- $\(\mathbf{J}\)$ 代表电流密度。
微分形式的安培定律表明，电流密度 $\(\mathbf{J}\)$ 产生了磁场强度 $\(\mathbf{B}\)$ 的旋度，描述了电流如何影响附近的磁场分布。

## Nabla-Operaltor


1. 梯度（Gradient）：

   $\nabla f = \frac{\partial f}{\partial x} \mathbf{i} + \frac{\partial f}{\partial y} \mathbf{j} + \frac{\partial f}{\partial z} \mathbf{k}$


2. 散度（Divergence）：
   $\nabla \cdot \mathbf{V} = \frac{\partial V_x}{\partial x} + \frac{\partial V_y}{\partial y} + \frac{\partial V_z}{\partial z}$

3. 旋度（Curl）：
   $\nabla \times \mathbf{V} = \left(\frac{\partial V_z}{\partial y} - \frac{\partial V_y}{\partial z}\right) \mathbf{i} + \left(\frac{\partial V_x}{\partial z} - \frac{\partial V_z}{\partial x}\right) \mathbf{j} + \left(\frac{\partial V_y}{\partial x} - \frac{\partial V_x}{\partial y}\right) \mathbf{k}$
