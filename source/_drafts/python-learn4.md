---
title: python 学习(四)
header_image: https://i.imgur.com/JjIQyzR.png 
abstract: python 字符串
tags:
- 技术
- PYTHON
---

> 所有序列操作对于字符串是同样适用，我们可以理解为将字符串里面的字符看成是序列的一个一个的元素。

# 格式化字符串
字符串中最核心的功能就是格式化操作。
## 字符串格式化基础
- 字符串格式话相当于字符串模板。通俗的讲就是，字符串中一段是固定而另一端是动态变化的。
- 那么固定的模块，我们称之为模板；动态的可以用`%`来替换。

  例如：
  ```python
  formatStr = 'hello %s.this is %s world'
  values = ('sisi', 'sisi')
  print(formatStr % values)

  >>>hello sisi.this is dasdad world
  ```
  >字符串模板指定格式化参数时，要使用`%`,指定字符串格式化参数值要使用元组。

- 使用`%f`来表示浮点类型的格式化参数
  ```python
  # 定义格式化模板
    from math import pi

    formatStr = 'PI是圆周率，%.4f ----->保留小数点%d位'
    values = (pi, 4)

    print(formatStr % values)
    >>> PI是圆周率，3.1416 ----->保留小数点4位

    formatStr1 = '%s的成功率%d%%'
    values1 = ('思思', 100)
    print(formatStr1 % values1)
    >>> 思思的成功率100%

    values2 = ('思思')
    print(formatStr1 % values2)

    >>> 参数值的数量要和格式化参数不匹配，error
  ```
  >记得参数值的数量要和格式化参数要匹配，不然会报错

## 模板字符串
>在**String**模块中提供了一个用于格式化的字符串**template**的类，用来处理同一个值替换所有的相同格式化参数。

- **template**格式化参数，用**$**符号来开头，后面接着格式化名称。
  ```python
  from string import Template

  a = Template('$ccc是我最喜欢的$ccc还是$ccc')
  print(a.substitute(ccc="python"))

  >>> python是我最喜欢的python还是python
  ```
- 当格式化参数是一个字符串一部分时，需要用`{}`来区分。
  ```python
  b = Template('${abv}RING')
  print(b.substitute(abv='sub'))
  >>> subRING
  ```

## 字符串中`format`方法
