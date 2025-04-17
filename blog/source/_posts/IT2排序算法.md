---
title: IT2排序算法
date: 2024-07.02 1:29:40
tags:
- Algorithmus
categories:
- Informationstechnik
- Algorithmus
mathjax: true
---

### Sort_A(A)

```python
1. Sort_A(A)
2.    for j = 2 to length[A]
3.       do key = A[j]
4.       i = j − 1
5.       while (i > 0 and A[i] > key)
6.           do A[i + 1] = A[i]
7.           i = i − 1
8.     A[i + 1] = key
```

**分析：**
- 这是典型的 **插入排序（Insertion Sort）**。
- 它通过将每个元素插入到已经排序的部分来排序整个数组。

**复杂度：**
- 最好情况（已经有序）：O(n)
- 最坏情况（反序）：O(n^2)
- 平均情况：O(n^2)

**特性：**
- **In-Place**：是的，插入排序是就地排序。
- **稳定性**：是的，插入排序是稳定的。
- **是否可中断**：是的，可以在任何时间点停止。

### Sort_B(A)

```python
1. Sort_B(A)
2.    B = elements[A] 1 upto A/2
3.    C = elements[A] A / 2 + 1 upto length[A]
4.    return function( Sort_B(B), Sort_B(C) )
5. 
6. Function(B, C)
7.    create new list D
8.    while B and C are not empty
9.    do if B[1] > C[1]
10.      then append C[1] to D and remove C[1]
11.      else append B[1] to D and remove B[1]
12.    return D
```

**分析：**
- 这是典型的 **归并排序（Merge Sort）**。
- 它将数组递归地分成两半，分别排序，然后合并。

**复杂度：**
- 最好情况：O(n log n)
- 最坏情况：O(n log n)
- 平均情况：O(n log n)

**特性：**
- **In-Place**：否，归并排序需要额外的空间来合并子数组。
- **稳定性**：是的，归并排序是稳定的。
- **是否可中断**：否，通常需要完成整个过程。

### Sort_C(A)

```python
1. Sort_C(A)
2.   for i = 1 to länge[A] - 1
3.       do for j = 1 to länge[A] - i
4.           do if A[j] > A[j + 1]
5.               vertausche A[j] mit A[j + 1]
```

**分析：**
- 这是典型的 **冒泡排序（Bubble Sort）**。
- 它通过重复地交换相邻元素来排序整个数组。

**复杂度：**
- 最好情况：O(n)（已经有序）
- 最坏情况：O(n^2)
- 平均情况：O(n^2)

**特性：**
- **In-Place**：是的，冒泡排序是就地排序。
- **稳定性**：是的，冒泡排序是稳定的。
- **是否可中断**：是的，可以在任何时间点停止。

### Sort_D(A, p, r)

```python
1. Sort_D( A, p, r )
2.   if p < r
3.      q = Function(A, p, r)
4.      Sort_D( A, p, q – 1 )
5.      Sort_D(A, q + 1, r)
6.   
7. Function(A, p, r)
8.    x = A[r]
9.    i = p – 1
10.   for j = p to r – 1
11.     do if A[j] <= x
12.        i = i + 1
13.        vertausche A[i] mit A[j]
14.     vertausche A[i + 1] mit A[r]
15.   return i + 1
```

**分析：**
A：要排序的数组。
p：当前排序部分的起始索引（通常是子数组的左边界）。
r：当前排序部分的结束索引（通常是子数组的右边界）。
- 这是典型的 **快速排序（Quick Sort）**。
- 它通过选择一个枢轴元素，将数组分成两部分，分别排序。

**复杂度：**
- 最好情况：O(n log n)
- 最坏情况：O(n^2)（枢轴总是最小或最大元素）
- 平均情况：O(n log n)

**特性：**
- **In-Place**：是的，快速排序是就地排序。
- **稳定性**：否，快速排序不是稳定的。
- **是否可中断**：否，通常需要完成整个过程。

### 小结

| 排序算法   | 复杂度 (最好情况) | 复杂度 (最坏情况) | 复杂度 (平均情况) | In-Place | 稳定性 | 是否可中断 |
| ---------- | ----------------- | ----------------- | ----------------- | -------- | ------ | ---------- |
| 插入排序   | O(n)              | O(n^2)            | O(n^2)            | 是       | 是     | 是         |
| 归并排序   | O(n log n)        | O(n log n)        | O(n log n)        | 否       | 是     | 否         |
| 冒泡排序   | O(n)              | O(n^2)            | O(n^2)            | 是       | 是     | 是         |
| 快速排序   | O(n log n)        | O(n^2)            | O(n log n)        | 是       | 否     | 否         |
