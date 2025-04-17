---
title: python学习笔记3
date: 2024-03.10 12:09:40
tags:
- python
categories:
- Informationstechnik
- python学习笔记
- python基础
mathjax: true
---
## 全局变量和局部变量

**全局变量**

在函数外部定义的变量，在程序的任何地方都可以访问和修改。

**局部变量**

在函数内部定义的变量，只能在该函数内部访问和修改。

**示例**

```python
# 定义全局变量
num = 10

def func():
    # 定义局部变量
    num = 20
    print(num)  # 输出: 20

func()

print(num)  # 输出: 10
```

**结论**

* 全局变量在整个程序范围内有效，局部变量只在函数内部有效。
* 在函数内部，如果存在与全局变量同名的局部变量，则优先使用局部变量。

**作用域**

变量的作用域是指变量可以被访问的范围。

* 全局变量的作用域是整个程序。
* 局部变量的作用域是其所在的函数内部。

**命名空间**

命名空间是用来存放变量的区域。

* Python 中每个函数都有自己的命名空间。
* 全局变量存放在全局命名空间中。

**示例**

```python
# 定义全局变量
num = 10

def func():
    # 定义局部变量
    num = 20
    print(num)  # 输出: 20

func()

print(num)  # 输出: 10

# 在另一个函数中，num 是另一个局部变量
def func2():
    num = 30
    print(num)  # 输出: 30

func2()
```

**输出:**

```
20
10
30
```
## 函数

**定义函数**

使用 `def` 关键字定义函数，函数名后跟括号，括号内可以列出参数，函数体由缩进表示。

**示例**

```python
def func(name):
    print("Hello, " + name)

func("John")  # 输出: Hello, John
```

**带参数的函数**

函数可以定义参数，用于接收外部数据。

**示例**

```python
def func(name, age):
    print("Hello, " + name + ". You are " + str(age) + " years old.")

func("John", 30)  # 输出: Hello, John. You are 30 years old.
```

**返回值**

函数可以使用 `return` 语句返回值。

**示例**

```python
def func(x, y):
    return x + y

result = func(1, 2)
print(result)  # 输出: 3
```

**多个返回值**

函数可以返回多个值，返回值以元组形式返回。

**示例**

```python
def func(x, y):
    return x + y, x - y

result1, result2 = func(1, 2)
print(result1, result2)  # 输出: 3 -1
```

**匿名函数**

可以使用 `lambda` 关键字定义匿名函数，匿名函数通常用于一次性操作。

**示例**

```python
# 定义匿名函数
func = lambda x, y: x + y

# 调用匿名函数
result = func(1, 2)
print(result)  # 输出: 3
```

### 进阶

* 可变参数函数
* 关键字参数函数
* 默认参数函数
* 递归函数

**可变参数函数**

可变参数函数允许接收任意数量的参数。

**示例**

```python
def func(*args):
    print(args)

func(1, 2, 3)  # 输出: (1, 2, 3)

# 可变参数也可以用于关键字参数
def func(name, *args):
    print(name, args)

func("John", 1, 2, 3)  # 输出: John (1, 2, 3)
```

**关键字参数函数**

关键字参数函数允许使用关键字来传递参数。

**示例**

```python
def func(name, age):
    print(name, age)

func(name="John", age=30)  # 输出: John 30

# 关键字参数也可以用于可变参数
def func(name, *args, **kwargs):
    print(name, args, kwargs)

func("John", 1, 2, 3, city="New York")  # 输出: John (1, 2, 3) {'city': 'New York'}
```

**默认参数函数**

默认参数函数允许为参数设置默认值。

**示例**

```python
def func(name, age=18):
    print(name, age)

func("John")  # 输出: John 18

func("John", 30)  # 输出: John 30
```

**递归函数**

递归函数是指在函数内部调用自身。

**示例**

```python
def func(n):
    if n == 0:
        return 1
    else:
        return n * func(n - 1)

result = func(5)
print
```

## 文件操作

**打开文件**

使用 `open()` 函数打开文件，该函数返回一个文件对象。

**示例**

```python
# 打开文件并读取内容
file = open("test.txt", "r")
content = file.read()
print(content)

# 关闭文件
file.close()
```

**写入文件**

使用 `write()` 方法写入文件。

**示例**

```python
# 打开文件并写入内容
file = open("test.txt", "w")
file.write("Hello, world!")

# 关闭文件
file.close()
```

**读取文件**

使用 `read()` 方法读取文件内容。

**示例**

```python
# 打开文件并读取内容
file = open("test.txt", "r")
content = file.read()
print(content)

# 关闭文件
file.close()
```

**其他方法**

* `readline()` 方法读取文件的一行内容。
* `readlines()` 方法读取文件的所有行内容，并返回一个列表。

**示例**

```python
# 打开文件并读取一行内容
file = open("test.txt", "r")
line = file.readline()
print(line)

# 关闭文件
file.close()

# 打开文件并读取所有行内容
file = open("test.txt", "r")
lines = file.readlines()
print(lines)

# 关闭文件
file.close()
```


### 进阶

* with 语句
* csv 文件操作
* json 文件操作

**with 语句**

使用 `with` 语句可以自动关闭文件，无需手动调用 `close()` 方法。

**示例**

```python
with open("test.txt", "r") as file:
    content = file.read()
    print(content)
```

**csv 文件操作**

csv 文件是逗号分隔值文件，可以使用 `csv` 模块操作 csv 文件。

**示例**

```python
import csv

# 读取 csv 文件
with open("test.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)

# 写入 csv 文件
with open("test.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerow(["姓名", "年龄"])
    writer.writerow(["John", 30])
```

**json 文件操作**

json 文件是 JavaScript 对象表示法文件，可以使用 `json` 模块操作 json 文件。

**示例**

```python
import json

# 读取 json 文件
with open("test.json", "r") as file:
    data = json.load(file)
    print(data)

# 写入 json 文件
with open("test.json", "w") as file:
    data = {"name": "John", "age": 30}
    json.dump(data, file)
```