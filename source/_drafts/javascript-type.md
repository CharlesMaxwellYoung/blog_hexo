---
title: javascript 冷知识
header_image:
abstract:
tags:
---

# 前言

运行时类型是代码实际执行过程中我们用到的类型。所有的类型的数据都会属于7个类型。从变量，参数、返回值到表达式的额中间结果。任何JavaScript运行产生的数据都会产生数据。

七种语言类型是：
- undefined
- null
- boolean
- string
- number
- symbol
- object
> symbol 是es6 新增

## undefined、null

> 首先提出一个问题为什么有的编程规范要求用 void 0 代替 undefined

1. Undefined 类型表示未定义，任何赋值之前都是undefined，我们也可以通过void 运算把任意一个表达式变成undefined值。
2. 因为是undefined是一个变量，这里是JavaScript语言公认的设计事物之一。因此为了避免被无意间修改，void 0 --> undefined
3. null 表示：定义了但是为空。
4. null类型只有一个值就是null。与undefined不同他是一个JavaScript关键字。

## string

> 表示文本数据。长度为2^53 - 1。

1. 这里需要确认一个概念就是：string 不是表示字符串。
2. 表示字符串的UTF16编码。

### number

