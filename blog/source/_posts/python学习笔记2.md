---
title: python学习笔记2
date: 2024-03.05 12:09:40
tags:
- python
categories:
- Informationstechnik
- python学习笔记
- python基础
mathjax: true
---

## Python 字符串

**字符串**

字符串是一串字符的集合。字符串可以使用单引号、双引号或三引号创建。

例如：

```python
str1 = 'Hello, world!'
str2 = "Hello, world!"
str3 = """Hello,
world!"""
```

**字符串的常见操作**

* 字符串拼接：可以使用 `+` 运算符连接两个字符串。
* 字符串切片：可以使用 `[]` 运算符截取字符串的一部分。
* 字符串查找：可以使用 `in` 运算符判断一个字符或字符串是否在另一个字符串中。
* 字符串替换：可以使用 `replace()` 方法替换字符串中的部分内容。

**示例：**

```python
# 字符串拼接
str1 = "Hello"
str2 = "world!"
print(str1 + str2)

# 字符串切片
str = "Hello, world!"
print(str[0:3])

# 字符串查找
str = "Hello, world!"
print("world" in str)

# 字符串替换
str = "Hello, world!"
print(str.replace("world", "Python"))
```

**输出结果：**

```
Hello world!
Hel
True
Hello Python!
```

**字符串的内置方法**

Python 内置了大量字符串方法，可以用于执行各种操作。

**常见字符串方法:**

* `upper()`：将字符串转换为大写
* `lower()`：将字符串转换为小写
* `title()`：将字符串的首字母转换为大写
* `capitalize()`：将字符串的首字母转换为大写，其他字母转换为小写
* `strip()`：删除字符串两端的空格
* `lstrip()`：删除字符串左端的空格
* `rstrip()`：删除字符串右端的空格
* `find()`：查找字符串中第一次出现指定字符或字符串的位置
* `rfind()`：查找字符串中最后一次出现指定字符或字符串的位置
* `replace()`：替换字符串中的部分内容

**示例：**

```python
str = "Hello, world!"

# 将字符串转换为大写
print(str.upper())

# 将字符串转换为小写
print(str.lower())

# 将字符串的首字母转换为大写
print(str.title())

# 将字符串的首字母转换为大写，其他字母转换为小写
print(str.capitalize())

# 删除字符串两端的空格
print(str.strip())

# 删除字符串左端的空格
print(str.lstrip())

# 删除字符串右端的空格
print(str.rstrip())

# 查找字符串中第一次出现指定字符或字符串的位置
print(str.find("world"))

# 查找字符串中最后一次出现指定字符或字符串的位置
print(str.rfind("!"))

# 替换字符串中的部分内容
print(str.replace("world", "Python"))
```

**输出结果：**

```
HELLO, WORLD!
hello, world!
Hello, World!
Hello, world!
Hello, world!
Hello,world!
Hello, world!
0
12
Hello Python!
```

## Python 元组

**元组**

元组是一种有序的集合，可以包含任何类型的数据。元组可以使用括号创建，元素之间用逗号分隔。

例如：

```python
tuple1 = (1, 2, 3)
tuple2 = ("a", "b", "c")
tuple3 = (1, "a", True)
```

**元组的特性**

* 元组是不可变的，一旦创建就不能修改。
* 元组可以使用索引访问元素。
* 元组可以使用切片操作截取部分元素。
* 元组可以使用 in 运算符判断元素是否存在。
* 元组可以使用 len() 函数获取元素个数。

**示例：**

```python
# 创建元组
tuple1 = (1, 2, 3)

# 访问元组元素
print(tuple1[0])

# 切片操作
print(tuple1[0:2])

# 判断元素是否存在
print("a" in tuple1)

# 获取元素个数
print(len(tuple1))
```

**输出结果：**

```
1
(1, 2)
False
3
```

## Python 列表

**列表**

列表是一种有序的集合，可以包含任何类型的数据。列表可以使用方括号创建，元素之间用逗号分隔。

**创建列表**

```python
# 创建空列表
list1 = []

# 创建包含元素的列表
list2 = [1, 2, 3]
list3 = ["a", "b", "c"]
list4 = [1, "a", True]
```

**访问列表元素**

可以使用索引访问列表元素，索引从 0 开始。

```python
# 访问第一个元素
print(list1[0])

# 访问最后一个元素
print(list2[-1])
```

**增删改操作**

* **添加元素**

可以使用 `append()` 方法添加元素到列表末尾，也可以使用 `insert()` 方法在指定位置插入元素。

```python
# 添加元素到列表末尾
list1.append(1)

# 在指定位置插入元素
list2.insert(1, "a")
```

* **删除元素**

可以使用 `remove()` 方法删除指定元素，也可以使用 `del` 关键字删除指定索引处的元素。

```python
# 删除指定元素
list1.remove(1)

# 删除指定索引处的元素
del list2[1]
```

* **修改元素**

可以直接修改列表元素的值。

```python
# 修改第一个元素
list1[0] = 2

# 修改第二个元素
list2[1] = "b"
```

**列表的常见操作**

* **加法运算**：两个列表可以相加，连接成一个新的列表。
* **乘法运算**：列表可以与数字相乘，重复指定的次数。
* **比较运算**：两个列表可以进行比较，比较规则与元组相同。
* **len() 函数**：获取列表元素个数
* **in 运算符**：判断元素是否存在
* **max() 函数**：获取列表最大值
* **min() 函数**：获取列表最小值
* **sort() 方法**：排序
* **reverse() 方法**：反转

**示例：**

```python
# 加法运算
list1 = [1, 2, 3]
list2 = [4, 5, 6]
print(list1 + list2)

# 乘法运算
list1 = [1, 2, 3]
print(list1 * 3)

# 比较运算
list1 = [1, 2, 3]
list2 = [1, 2, 4]
print(list1 < tuple2)

# 获取列表元素个数
list1 = [1, 2, 3]
print(len(list1))

# 判断元素是否存在
list1 = [1, 2, 3]
print("a" in list1)

# 获取列表最大值
list1 = [1, 2, 3]
print(max(list1))

# 获取列表最小值
list1 = [1, 2, 3]
print(min(list1))

# 排序
list1 = [3, 2, 1]
list1.sort()
print(list1)

# 反转
list1 = [1, 2, 3]
list1.reverse()
print(list1)
```

**输出结果：**

```
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 1, 2, 3, 1, 2, 3]
True
3
False
3
1
[1, 2, 3]
[3, 2, 1]
```
## Python 字典操作

**创建字典**

* 使用大括号创建空字典：

```python
dict1 = {}
```

* 使用大括号创建包含键值对的字典：

```python
dict2 = {"name": "John", "age": 30}
dict3 = {"a": 1, "b": 2, "c": 3}
```

**访问字典元素**

* 使用键访问字典元素：

```python
# 访问键 "name" 对应的值
print(dict2["name"])

# 访问键 "b" 对应的值
print(dict3["b"])
```

**增删改操作**

* **添加元素**

    * 使用 `update()` 方法添加键值对：

```python
dict2.update({"age": 31})
```

    * 使用 `setdefault()` 方法设置默认值：

```python
dict3.setdefault("c", 4)
```

* **删除元素**

    * 使用 `pop()` 方法删除指定键对应的值：

```python
dict2.pop("name")
```

    * 使用 `del` 关键字删除指定键：

```python
del dict3["b"]
```

* **修改元素**

直接修改字典元素的值：

```python
# 修改键 "age" 对应的值
dict2["age"] = 32

# 修改键 "c" 对应的值
dict3["c"] = 5
```

**查**

* **len() 函数**：获取字典元素个数

```python
dict1 = {"a": 1, "b": 2, "c": 3}
print(len(dict1))
```

* **in 运算符**：判断键是否存在

```python
dict1 = {"a": 1, "b": 2, "c": 3}
print("a" in dict1)
```

* **get() 方法**：获取键对应的值，如果键不存在则返回默认值

```python
dict1 = {"a": 1, "b": 2, "c": 3}
print(dict1.get("d", 4))
```

* **keys() 方法**：获取所有键

```python
dict1 = {"a": 1, "b": 2, "c": 3}
print(dict1.keys())
```

* **values() 方法**：获取所有值

```python
dict1 = {"a": 1, "b": 2, "c": 3}
print(dict1.values())
```

* **items() 方法**：获取所有键值对

```python
dict1 = {"a": 1, "b": 2, "c": 3}
print(dict1.items())
```

**示例**

```python
# 创建字典
dict1 = {"name": "John", "age": 30, "city": "New York"}

# 访问元素
print(dict1["name"])  # 输出: John

# 添加元素
dict1.update({"job": "Software Engineer"})

# 删除元素
del dict1["city"]

# 修改元素
dict1["age"] = 31

# 查找元素
print("name" in dict1)  # 输出: True

# 获取所有键
print(dict1.keys())  # 输出: dict_keys(['name', 'age', 'job'])

# 获取所有值
print(dict1.values())  # 输出: dict_values(['John', 31, 'Software Engineer'])

# 获取所有键值对
print(dict1.items())  # 输出: dict_items([('name', 'John'), ('age', 31), ('job', 'Software Engineer')])
```
## Python 元组操作

**创建元组**

* 使用括号创建空元组：

```python
tuple1 = ()
```

* 使用括号创建包含元素的元组：

```python
tuple2 = (1, 2, 3)
tuple3 = ("a", "b", "c")
tuple4 = (1, "a", True)
```

**访问元组元素**

* 使用索引访问元组元素，索引从 0 开始：

```python
# 访问第一个元素
print(tuple2[0])

# 访问最后一个元素
print(tuple3[-1])
```

**增删操作**

* **添加元素**

元组是不可变的，**不能直接添加元素**。

* **删除元素**

* 使用 `del` 关键字删除指定索引处的元素：

```python
# 删除第二个元素
del tuple2[1]
```

**元组的常见操作**

* **len() 函数**：获取元组元素个数

```python
tuple1 = (1, 2, 3)
print(len(tuple1))
```

* **in 运算符**：判断元素是否存在

```python
tuple1 = (1, 2, 3)
print(2 in tuple1)
```

* **+ 运算符**：连接两个元组

```python
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)
print(tuple1 + tuple2)
```

* *** 运算符**：重复指定次数

```python
tuple1 = (1, 2, 3)
print(tuple1 * 3)
```

* **max() 函数**：获取元组最大值

```python
tuple1 = (1, 2, 3)
print(max(tuple1))
```

* **min() 函数**：获取元组最小值

```python
tuple1 = (1, 2, 3)
print(min(tuple1))
```

**示例**

```python
# 创建元组
tuple1 = (1, 2, 3, 4, 5)

# 访问元素
print(tuple1[0])  # 输出: 1
print(tuple1[-1])  # 输出: 5

# 删除元素
del tuple1[2]

# 常见操作
print(len(tuple1))  # 输出: 3
print(2 in tuple1)  # 输出: True
print(tuple1 + (6, 7))  # 输出: (1, 2, 4, 5, 6, 7)
print(tuple1 * 3)  # 输出: (1, 2, 4, 5, 1, 2, 4, 5, 1, 2, 4, 5)
print(max(tuple1))  # 输出: 5
print(min(tuple1))  # 输出: 1
```
## Python 集合

**集合**

集合是一种无序的、不重复元素的集合。集合可以使用大括号创建，元素之间用逗号分隔。

**创建集合**

* 使用大括号创建空集合：

```python
set1 = {}
```

* 使用大括号创建包含元素的集合：

```python
set2 = {1, 2, 3}
set3 = {"a", "b", "c"}
set4 = {1, "a", True}
```

**集合的常见操作**

* **len() 函数**：获取集合元素个数

```python
set1 = {1, 2, 3}
print(len(set1))
```

* **in 运算符**：判断元素是否存在

```python
set1 = {1, 2, 3}
print(2 in set1)
```

* **& 运算符**：交集

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}
print(set1 & set2)
```

* **| 运算符**：并集

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}
print(set1 | set2)
```

* **- 运算符**：差集

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}
print(set1 - set2)
```

* **^ 运算符**：对称差

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}
print(set1 ^ set2)
```

* **add() 方法**：添加元素

```python
set1 = {1, 2, 3}
set1.add(4)
print(set1)
```

* **remove() 方法**：删除元素

```python
set1 = {1, 2, 3}
set1.remove(2)
print(set1)
```

* **pop() 方法**：随机删除元素

```python
set1 = {1, 2, 3}
set1.pop()
print(set1)
```

* **clear() 方法**：清空集合

```python
set1 = {1, 2, 3}
set1.clear()
print(set1)
```

**示例**

```python
# 创建集合
set1 = {1, 2, 3, 4, 5}

# 常见操作
print(len(set1))  # 输出: 5
print(2 in set1)  # 输出: True
print({1, 2, 3} & {2, 3, 4})  # 输出: {2, 3}
print({1, 2, 3} | {2, 3, 4})  # 输出: {1, 2, 3, 4}
print({1, 2, 3} - {2, 3, 4})  # 输出: {1}
print({1, 2, 3} ^ {2, 3, 4})  # 输出: {1, 4}

# 增删改
set1.add(6)
print(set1)  # 输出: {1, 2, 3, 4, 5, 6}

set1.remove(3)
print(set1)  # 输出: {1, 2, 4, 5, 6}

set1.pop()
print(set1)  # 输出: {1, 2, 4, 5}

set1.clear()
print(set1)  # 输出: set()
```

