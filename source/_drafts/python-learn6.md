---
title: python 学习(五)
thumbnail: 'https://i.imgur.com/JjIQyzR.png'
toc: true
tags:
  - PYTHON
categories:
  - 学习
---

>本次介绍 python 函数的使用。

<!-- more -->

# 函数基础

> 我们写程度都是一个一个的片段，所以我们需要将某些功能封装到整体内，并且命名的方式，说明这块区域干什么用的。

## 创建函数
- 定义函数采用关键字`def`:

```python
def greet():
    return "函数"
```

- 我们来写一个斐波那契的函数

```python
# 斐波拉契数
def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        print(b)
        a, b = b, a + b
        n = n + 1
    return 'none'
print(fib(3))
--->
0
1
1
2
none
```

## 函数添加文档注释

> 添加文档注释，可以充分说明，当前的函数是干嘛的。

