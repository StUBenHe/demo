---
title: python学习笔记1
date: 2024-03.01 12:09:40
tags:
- python
categories:
- Informationstechnik
- python学习笔记
- python基础
mathjax: true
---

## Python基础：输出、输入和判断

**输出**

Python使用`print()`函数进行输出。`print()`函数可以输出各种类型的数据，包括字符串、数字、列表、字典等。

例如：

```python
print("Hello, world!")
print(123)
print([1, 2, 3])
print({"name": "John", "age": 30})
```

输出结果：

```
Hello, world!
123
[1, 2, 3]
{'name': 'John', 'age': 30}
```

**输入**

Python使用`input()`函数进行输入。`input()`函数会提示用户输入内容，并返回用户输入的字符串。

例如：

```python
name = input("请输入你的名字：")
age = input("请输入你的年龄：")

print("你的名字是：", name)
print("你的年龄是：", age)
```

输出结果：

```
请输入你的名字：John
请输入你的年龄：30
你的名字是： John
你的年龄是： 30
```

**判断**

Python使用`if`语句进行判断。`if`语句可以根据条件判断执行不同的代码。

例如：

```python
age = int(input("请输入你的年龄："))

if age >= 18:
    print("你是成年人")
else:
    print("你是未成年人")
```

输出结果：

```
请输入你的年龄：18
你是成年人
```

## Python 中的 for 和 while 循环

**for 循环**

for 循环用于遍历一个可迭代对象，例如列表、字符串、元组等。for 循环的语法如下：

```python
for <variable> in <iterable>:
    <code block>
```

其中：

* `<variable>`: 循环变量，用于保存可迭代对象的每个元素
* `<iterable>`: 可迭代对象，例如列表、字符串、元组等
* `<code block>`: 循环体，在每次循环中执行

**示例：**

```python
# 遍历一个列表
for i in range(10):
    print(i)

# 遍历一个字符串
for char in "Hello, world!":
    print(char)
```

输出结果：

```
0
1
2
3
4
5
6
7
8
9
H
e
l
l
o
,
 
w
o
r
l
d
!
```

**while 循环**

while 循环用于根据条件反复执行一段代码。while 循环的语法如下：

```python
while <condition>:
    <code block>
```

其中：

* `<condition>`: 循环条件，决定是否继续执行循环
* `<code block>`: 循环体，在每次循环中执行

**示例：**

```python
# 循环输出 1 到 100 的偶数
i = 1
while i <= 100:
    if i % 2 == 0:
        print(i)
    i += 1
```

输出结果：

```
2
4
6
...
98
100
```

**for 和 while 循环的区别:**

* for 循环用于遍历可迭代对象，而 while 循环用于根据条件反复执行一段代码
* for 循环的循环次数是固定的，而 while 循环的循环次数是不固定的
* for 循环通常用于遍历列表、字符串等可迭代对象，而 while 循环通常用于需要根据条件反复执行一段代码的情况
