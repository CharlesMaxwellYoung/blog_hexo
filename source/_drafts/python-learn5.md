---
title: python 学习(五)
thumbnail: 'https://i.imgur.com/1yLFPcB.png'
tags:
  - PYTHON
categories:
  - 学习
---

> 字典,类似于javascript 中的map 对象
>

<!-- more -->

## 创建和使用字典 `dict` 函数
1.字典可以用下面的创建

```python
phoneBook = {"bill":"1234","MIKE":"312312"}
```
>字典的 key 值是唯一的。

2.可以用 dict 函数，通过其他映射（如其他的字段）或简直对的序列建立字典
```python
items = [["billl","21312321"],(321321,"3213"),["martty","dsada"]]
print(dict(items))
>>> {'billl': '21312321', 321321: '3213', 'martty': 'dsada'}
```
> 第一个值表示 key，第二个值标识 value

3.dict 函数还可以通过关键字参数来创建字典
```python
a = dict(name="312321", number="222", age=111)
print(dict(a))
>>> {'name': '312321', 'number': '222', 'age': 111}
```
>如果 dict 函数如果不指定参数，那么该函数会返回一个空的字典

## 字典的基本操作

1.如下：
```python

dict = {}  # 定义一个字典
dict[20] = "Bill"  # 向字典 dict 中添加整数类型的key
dict["Mike"] = {'age': 30, "salary": 3000}  # 向字典 dict 中添加字符串的key
dict[(12, "Mike", True)] = "hello"  # 向字典 dict 中添加元组类型的key
print(dict)
>>> {20: 'Bill', 'Mike': {'age': 30, 'salary': 3000}, (12, 'Mike', True): 'hello'}
```
2. in 操作，检查 dict 中是否包含有健为 `key`的项，只能查找 key ，不是 value
```python
Demo = {
    "sublime": {
        "language": ["java", "python"],
        "org": "sublime 开源"
    },
    "webstorm": {
        "language": ["python", "php"],
        "org": "webstorm 基金会"
    },
    "vs code": {
        "language": ["javascript"],
        "org": "javascript 开源"
    }
}

de = input("请输入的编辑器名字")
de1 = de.replace(" ", " ").lower()
# 检查 dict 中是否包含有健为 key 的项
if de1 in Demo:
    print(Demo[de1])

>>> 请输入的编辑器名字webstorm
    {'language': ['python', 'php'], 'org': 'webstorm 基金会'}
```

## 字典的格式化字符串

1.对字典对字符串进行格式化，并且使用元组和`%`对字符串进行格式化的方式对比

```python
values = (1, 3, "dsada")
str1 = "%d dsada,   xyt %d,  %s world"
print(str1 % values)
>>> 1 dsada,   xyt 3,  dsada world
```

> 使用%和元组格式化字符串

2.定义字符串模板

```python
values1 = {"title": "webstorm", "url": "https://www.baidu.com"}
str2 = """

<html>
    <title>{title}</title>
    <body>
        <a href="{url}"></a>
    </body>
</html>

"""
print(str2.format_map(values1))

>>>
<html>
    <title>webstorm</title>
    <body>
        <a href="https://www.baidu.com"></a>
    </body>
</html>
```

> `format_map`方法使用的字符串模板中，格式化采用一对花括号`{}`,如果格式化模板中的格式化参数在字典中为找到，系统会抛出异常。

## 序列与迭代

1.获取字段中key的列表

```python
dict = {"x": 1, "y": 2, "z": 7}

for a in dict:
    print(a)
>>>
x
y
z
```

2.同时获取字典中的key和value列表

```python
for a, y in dict.items():
    print(a, y)
>>>
x 1
y 2
z 7
```

>使用字典中的**items**方法，转换为元组的序列 `dict_items([('x', 1), ('y', 2), ('z', 7)])`

3.并行迭代

同时迭代的两个或多个序列,用range函数获取序列索引的范围

```python
names = ["bill", "marry", "john"]
ages = [30, 40, 60]

for i in range(len(names)):
    print(names[i], ages[i], end=" ")
>>> bill 30 marry 40 john 60
```

4.压缩序列

