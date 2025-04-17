---
title: pandas学习笔记2
date: 2024-03.15 1:29:40
tags:
- python
- pandas
categories:
- Informationstechnik
- python学习笔记
- pandas
mathjax: true
---



## Matplotlib 作图

Matplotlib 是 Python 中一个常用的绘图库，可以用来绘制各种类型的图表，例如折线图、柱状图、饼图、散点图等。

**安装 Matplotlib**

```python
pip install matplotlib
```

**基本绘图**

```python
import matplotlib.pyplot as plt

# 绘制折线图
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)

# 添加标题
plt.title('折线图')

# 添加 x 轴标签
plt.xlabel('x')

# 添加 y 轴标签
plt.ylabel('y')

# 显示图形
plt.show()
```

**其他类型图表**

* 柱状图：

```python
plt.bar(x, y)
```

* 饼图：

```python
plt.pie(y)
```

* 散点图：

```python
plt.scatter(x, y)
```

**高级绘图**

Matplotlib 还提供了许多高级功能，例如：

* 子图：

```python
plt.subplot(121)
plt.plot(x, y)

plt.subplot(122)
plt.bar(x, y)

plt.show()
```

* 图例：

```python
plt.plot(x, y, label='Line')
plt.bar(x, y, label='Bar')

plt.legend()

plt.show()
```

* 3D 图形：

```python
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x, y, z = np.linspace(0, 10, 100), np.linspace(0, 10, 100), np.linspace(0, 10, 100)

ax.plot_wireframe(x, y, z)

plt.show()
```

**参考**

* Matplotlib 官方文档: [https://matplotlib.org/](https://matplotlib.org/)
* Matplotlib 教程: [https://matplotlib.org/stable/tutorials/index.html](https://matplotlib.org/stable/tutorials/index.html)

**示例**

```python
# 折线图
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)

plt.title('折线图')

plt.xlabel('x')

plt.ylabel('y')

plt.show()

# 柱状图
plt.bar(x, y)

plt.title('柱状图')

plt.xlabel('x')

plt.ylabel('y')

plt.show()

# 饼图
plt.pie(y)

plt.title('饼图')

plt.show()

# 散点图
plt.scatter(x, y)

plt.title('散点图')

plt.xlabel('x')

plt.ylabel('y')

plt.show()

# 子图
plt.subplot(121)
plt.plot(x, y)

plt.subplot(122)
plt.bar(x, y)

plt.show()

# 图例
plt.plot(x, y, label='Line')
plt.bar(x, y, label='Bar')

plt.legend()

plt.show()

# 3D 图形
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x, y, z = np.linspace(0, 10, 100), np.linspace(0, 10, 100), np.linspace(0, 10, 100)

ax.plot_wireframe(x, y, z)

plt.show()
```


## 数据合并简介

数据合并是指将两个或多个数据集组合在一起的过程，是数据分析中的重要操作。它可以用于整合来自不同来源的数据，以便进行更深入的分析。

### 常用合并方法：

**1. concat:**

* 按行或列连接两个或多个DataFrame。
* 常用于将具有相同列名的DataFrame合并在一起。
* 支持多个连接轴，例如 `axis=0` 表示按行连接，`axis=1` 表示按列连接。
* 可以使用 `ignore_index` 参数来忽略原始DataFrame的索引。

**示例:**

```python
df1 = pd.DataFrame({'name': ['Alice', 'Bob'], 'age': [25, 30]})
df2 = pd.DataFrame({'city': ['London', 'Paris']})

# 按列连接
df_concat_cols = pd.concat([df1, df2], axis=1)

# 按行连接
df_concat_rows = pd.concat([df1, df2], axis=0, ignore_index=True)

print(df_concat_cols)

# Output:
#   name  age  city
# 0  Alice   25  London
# 1   Bob   30  Paris

print(df_concat_rows)

# Output:
#    name  age  city
# 0  Alice   25  NaN
# 1   Bob   30  NaN
# 2  NaN   NaN  London
# 3  NaN   NaN  Paris
```

**2. append:**

* 将一个DataFrame追加到另一个DataFrame的末尾。
* 常用于将具有相同列名的DataFrame追加在一起。
* 可以使用 `ignore_index` 参数来忽略原始DataFrame的索引。

**示例:**

```python
df3 = pd.DataFrame({'name': ['Charlie'], 'age': [28]})

df_append = df1.append(df3, ignore_index=True)

print(df_append)

# Output:
#    name  age
# 0  Alice   25
# 1   Bob   30
# 2  Charlie  28
```

**3. merge:**

* 根据共同列将两个DataFrame合并在一起。
* 常用于将具有不同列名的DataFrame合并在一起。
* 可以使用 `on` 参数指定要合并的列。
* 可以使用 `how` 参数指定连接类型，例如 `inner` 表示仅保留匹配行，`left` 表示保留所有左DataFrame中的行，`right` 表示保留所有右DataFrame中的行，`outer` 表示保留所有行。

**示例:**

```python
df_employees = pd.DataFrame({'name': ['Alice', 'Bob', 'Charlie'], 'department': ['Sales', 'Marketing', 'Sales']})
df_salaries = pd.DataFrame({'name': ['Alice', 'Bob', 'Diana'], 'salary': [25000, 30000, 35000]})

# 内连接，仅保留匹配行
df_merged_inner = pd.merge(df_employees, df_salaries, on='name', how='inner')

# 左连接，保留所有左DataFrame中的行
df_merged_left = pd.merge(df_employees, df_salaries, on='name', how='left')

# 右连接，保留所有右DataFrame中的行
df_merged_right = pd.merge(df_employees, df_salaries, on='name', how='right')

# 外连接，保留所有行
df_merged_outer = pd.merge(df_employees, df_salaries, on='name', how='outer')

print(df_merged_inner)

# Output:
#   name  department  salary
# 0  Alice      Sales   25000
# 1   Bob  Marketing   30000

print(df_merged_left)

# Output:
#   name  department  salary
# 0  Alice      Sales   25000
# 1   Bob  Marketing   30000
# 2  Charlie     Sales    NaN

print(df_merged_right)

# Output:
#   name  department  salary
# 0  Alice      Sales   25000
# 1   Bob  Marketing   30000
# 2  Diana        NaN   35000

print(df_merged_outer)

# Output:
#   name  department  salary
# 0  Alice      Sales   25000
# 1   
```



## 数据聚合

数据聚合是将多个数据点组合成一个更概括的值的过程。它通常用于分析数据并提取有意义的见解。

### 常用聚合函数：

* **求和:** `sum()`
* **求平均值:** `mean()`
* **求中位数:** `median()`
* **求最大值:** `max()`
* **求最小值:** `min()`
* **计数:** `count()`
* **标准差:** `std()`
* **方差:** `var()`

### 使用示例：

```python
import pandas as pd

data = {'name': ['Alice', 'Bob', 'Charlie'], 'age': [25, 30, 28], 'city': ['London', 'Paris', 'London']}
df = pd.DataFrame(data)

# 按列求和
df_sum = df.sum()

# 按列求平均值
df_mean = df.mean()

# 按列求中位数
df_median = df.median()

# 按列求最大值
df_max = df.max()

# 按列求最小值
df_min = df.min()

# 按列计数
df_count = df.count()

# 按列求标准差
df_std = df.std()

# 按列求方差
df_var = df.var()

print(df_sum)

# Output:
# name      AliceBobCharlie
# age        83
# city    LondonParisLondon

print(df_mean)

# Output:
# name    AliceBobCharlie
# age        25.333333
# city    LondonParisLondon

print(df_median)

# Output:
# name    Alice
# age      28.0
# city    London

print(df_max)

# Output:
# name    Charlie
# age        30
# city    Paris

print(df_min)

# Output:
# name    Alice
# age        25
# city    London

print(df_count)

# Output:
# name    3
# age    3
# city    3

print(df_std)

# Output:
# name    2.081666
# age      2.872020
# city    0.000000

print(df_var)

# Output:
# name     4.333333
# age      8.230769
# city    0.000000
```

### 进阶：

* 可以使用 `groupby()` 函数对数据进行分组，然后应用聚合函数。
* 可以使用多个聚合函数同时聚合数据。
* 可以使用 lambda 函数自定义聚合函数。

