---
title: pandas学习笔记1
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


## pandas 的 Series

**简介**

Series 是 pandas 中一维的数据结构，类似于 NumPy 的 ndarray，但具有更丰富的功能。它可以存储任何类型的数据，包括数字、字符串、日期、时间等。

**创建 Series**

可以使用以下方法创建 Series：

* 从列表或元组创建：

```python
import pandas as pd

s = pd.Series([1, 2, 3])

print(s)

# 输出：
# 0    1
# 1    2
# 2    3
# dtype: int64
```

* 从字典创建：

```python
s = pd.Series({'a': 1, 'b': 2, 'c': 3})

print(s)

# 输出：
# a    1
# b    2
# c    3
# dtype: int64
```

* 从 NumPy 数组创建：

```python
import numpy as np

s = pd.Series(np.array([1, 2, 3]))

print(s)

# 输出：
# 0    1
# 1    2
# 2    3
# dtype: int64
```

**属性和方法**

Series 具有许多属性和方法，用于访问和操作数据。

* **属性**

    * `index`：索引，标识每个元素的位置
    * `values`：值，存储在 Series 中的数据
    * `dtype`：数据类型
    * `shape`：形状，包含 Series 的长度
    * `ndim`：维度数，对于 Series 始终为 1

* **方法**

    * `head(n)`：返回前 n 个元素
    * `tail(n)`：返回后 n 个元素
    * `iloc[n]`：通过索引位置获取元素
    * `loc[key]`：通过标签获取元素
    * `sort_values()`：根据值排序
    * `describe()`：统计描述

**示例**

```python
# 访问索引
print(s.index)

# 输出：
# RangeIndex(start=0, stop=3, step=1)

# 访问值
print(s.values)

# 输出：
# [1 2 3]

# 访问数据类型
print(s.dtype)

# 输出：
# int64

# 访问形状
print(s.shape)

# 输出：
# (3,)

# 访问维度数
print(s.ndim)

# 输出：
# 1

# 获取前两个元素
print(s.head(2))

# 输出：
# 0    1
# 1    2
# dtype: int64

# 获取后两个元素
print(s.tail(2))

# 输出：
# 1    2
# 2    3
# dtype: int64

# 通过索引位置获取元素
print(s.iloc[1])

# 输出：
# 2

# 通过标签获取元素
print(s.loc['b'])

# 输出：
# 2

# 根据值排序
print(s.sort_values())

# 输出：
# 0    1
# 1    2
# 2    3
# dtype: int64

# 统计描述
print(s.describe())

# 输出：
# count    3.000000
# mean     2.000000
# std      1.000000
# min      1.000000
# 25%      1.500000
# 50%      2.000000
# 75%      2.500000
# max      3.000000
```

**总结**

Series 是 pandas 中一维的数据结构，具有丰富的功能，可以用于存储和操作各种类型的数据。

## pandas 的 DataFrame

**简介**

pandas 的 DataFrame 是一个二维的、大小可变的、由数据表格构成的 자료结构，类似于电子表格软件中的工作表。它由行和列组成，其中每行代表一条数据记录，每列代表一个变量。

**创建 DataFrame**

有多种方法可以创建 DataFrame：

* 从列表或字典创建：

```python
import pandas as pd

# 从列表创建
data = [
    ['A1', 1, 2.5],
    ['A2', 3, 4.2],
    ['A3', 5, 6.1]
]

df = pd.DataFrame(data, columns=['name', 'age', 'score'])

print(df)

# 输出：
#       name  age  score
# 0     A1    1   2.50
# 1     A2    3   4.20
# 2     A3    5   6.10

# 从字典创建
data = {'name': ['A1', 'A2', 'A3'], 'age': [1, 3, 5], 'score': [2.5, 4.2, 6.1]}

df = pd.DataFrame(data)

print(df)

# 输出：
#       name  age  score
# 0     A1    1   2.50
# 1     A2    3   4.20
# 2     A3    5   6.10
```

* 从 CSV 文件读取：

```python
df = pd.read_csv('data.csv')
```

* 从 NumPy 数组创建：

```python
import numpy as np

data = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

df = pd.DataFrame(data, columns=['col1', 'col2', 'col3'])

print(df)

# 输出：
#   col1  col2  col3
# 0    1     2     3
# 1    4     5     6
# 2    7     8     9
```

**访问数据**

* 通过列名访问：

```python
print(df['name'])
```

* 通过行索引访问：

```python
print(df.iloc[1])  # 通过位置索引
print(df.loc['A2'])  # 通过标签索引
```

**操作数据**

DataFrame 提供了丰富的功能进行数据操作，例如：

* `assign()`：添加列
* `drop()`：删除列
* `loc()`：修改行
* `sort_values()`：排序
* `query()`：过滤
* `pivot_table()`：数据透视表
* `concat()`：合并
* `join()`：连接

**示例**

```python
# 添加列
df['grade'] = ['A', 'B', 'C']

# 删除列
df = df.drop('grade', axis=1)

# 修改行
df.loc[0, 'age'] = 2

# 排序
df = df.sort_values(by='score', ascending=False)

# 过滤
df_filtered = df[df['age'] > 2]

# 数据透视表
df_pivot = df.pivot_table(index='name', columns='age', values='score', aggfunc=np.mean)

# 合并
df1 = pd.DataFrame({'name': ['A', 'B'], 'age': [1, 2]})
df2 = pd.DataFrame({'score': [3, 4]})

df_concat = pd.concat([df1, df2], axis=1)

df_join = df1.join(df2, on='name')

print(df)
print(df_filtered)
print(df_pivot)
print(df_concat)
print(df_join)
```
```
       name  age  score
0     A1    2   2.50
1     A2    3   4.20
2     A3    5   6.10

       name  age  score
1     A2    3   4.20
2     A3    5   6.10

name  age
A1    2
A2    3
A3    5

       name  age  score
2     A3    5   6.10
1     A2    3   4.20

   name  age  score
0  A1     2  2.500000
1  A2     3  4.200000
2  A3     5  6.100000

   name  age  score
0  A1     2   2.5
1  A2     3   4.2
2  A3     5   6.1

   name  age  score
0  A1     2   2.5
1  A2     3   4.2
2  A3     5   6.1
```

**解释**

* 添加列：`df['grade'] = ['A', 'B', 'C']` 语句为 DataFrame 添加了一列名为 `grade` 的列，该列包含值 `['A', 'B', 'C']`。
* 删除列：`df = df.drop('grade', axis=1)` 语句删除了 DataFrame 中名为 `grade` 的列。
* 修改行：`df.loc[0, 'age'] = 2` 语句将 DataFrame 中第一行的 `age` 值修改为 2。
* 排序：`df = df.sort_values(by='score', ascending=False)` 语句根据 `score` 列对 DataFrame 进行降序排序。
* 过滤：`df_filtered = df[df['age'] > 2]` 语句过滤出 `age` 值大于 2 的行。
* 数据透视表：`df_pivot = df.pivot_table(index='name', columns='age', values='score', aggfunc=np.mean)` 语句以 `name` 列为索引，以 `age` 列为列，以 `score` 列为值，并使用 `np.mean` 函数计算平均值，创建数据透视表。
* 合并：`df_concat = pd.concat([df1, df2], axis=1)` 语句将 `df1` 和 `df2` 按照水平方向合并，形成新的 DataFrame。
* 连接：`df_join = df1.join(df2, on='name')` 语句根据 `name` 列连接 `df1` 和 `df2`，形成新的 DataFrame。


**总结**

DataFrame 是 pandas 的核心数据结构，功能强大，能够高效地处理各种表格型数据。通过它，我们可以轻松地完成数据清洗、转换、分析等操作。

**进阶**

* 可以使用 `groupby()` 方法对 DataFrame 进行分组操作。
* 可以使用 `apply()` 方法对 DataFrame 中的每个元素进行自定义操作。
* 可以使用 `lambda` 表达式进行简化操作。



## pandas 中的 iloc

**简介**

`iloc` 是 pandas DataFrame 中的一个属性，用于基于整数的索引和选择。它允许您使用 DataFrame 中的位置（索引）来访问和修改数据。

**功能**

* **通过位置访问数据:** 您可以使用 `iloc` 访问单个元素、行或基于其在 DataFrame 中的整数位置的一组行/列。
* **修改:** `iloc` 也可以用于修改 DataFrame 中的数据。

**语法:**

```python
df.iloc[row_index]        # 访问单个元素或整行
df.iloc[row_start:row_end]  # 访问行切片（包含开始，不包含结束）
df.iloc[[row_index1, row_index2]]  # 按位置访问特定行
df.iloc[:, column_index]    # 访问整列
df.iloc[row_slice, column_slice]  # 使用切片访问特定行和列
```

**示例:**

```python
import pandas as pd

data = {'name': ['Alice', 'Bob', 'Charlie'], 'age': [25, 30, 28]}
df = pd.DataFrame(data)

# 访问单个元素
first_name = df.iloc[0, 0]  # 访问索引 0（第一行）和列 0（第一列）处的姓名
age = df.iloc[1]            # 访问索引 1（第二行）处的整行

# 访问行切片
first_two_rows = df.iloc[:2]  # 获取前两行（0 和 1）

# 访问特定行
specific_rows = df.iloc[[0, 2]]  # 获取索引 0 和 2 处的行

# 访问整列
age_col = df.iloc[:, 1]    # 获取 'age' 列（第二列）

# 访问特定行和列
subset_df = df.iloc[[0, 1], 1]  # 获取行 0 和 1 的 'age' 列（第二列）
```

**要点:**

* `iloc` 使用 DataFrame 中的整数位置（索引）来访问/修改数据。
* 与基于标签的索引 (`loc`) 相比，它提供了一种更简洁的方式来按位置访问数据。
* 可以使用负数索引来访问末尾的元素（例如，`df.iloc[-1]`）。

**其他说明:**

* 对于基于标签的索引，请使用 `loc`.
* `iloc` 也可以用于设置 DataFrame 中的值。

**总结**

`iloc` 是 pandas DataFrame 中一个强大的工具，用于基于整数的索引和选择。它可以帮助您轻松地访问和修改数据，并进行各种数据分析操作。

**进阶**

* 使用 `iloc` 和 `iat` 属性来访问和修改单个元素。
* 使用 `iloc` 和 `assign` 方法来添加或修改列。
* 使用 `iloc` 和 `isin` 方法来过滤行。

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