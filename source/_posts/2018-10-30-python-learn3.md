---
layout: post
title: "python 学习(三)"
header_image: https://i.imgur.com/JjIQyzR.png
abstract: python 序列中列表和元组
tags: 
- 技术
- PYTHON
---
# 基础知识

> 在python中最基本的数据结构是序列。系列的每一个元素都被分配一个编号，可以称这个编号是索引。
> 自己可以理解为其他语言的数组
# 序列

## 1.创建序列

创建一个序列：

```python
a = [1, 3, "3", True]
```

> 序列的内部值是任意类型的值

创建二维序列：

```python
v = [1, 3, 45, [1, "4324"]]
```
## 2.序列的基本操作

- 和其他语言一样，序列都是下标的。

  ```python
  a = [1, 3, "3", True]
  print(a[1])
  
  >>>3
  ```

- 可以通过索引获取字符串s中，相对应的位置的字符，类似js操作

  ```python
  s = 'hello world'
  print(s[2])
  
  >>>l
  ```

- 如果索引为负数，则获取序列的倒数第一和第二，例如：

  ```python
  s = ["bill", 'mary', 'jack']
  print(s[0])
  print(s[-1])
  print(s[-2])
  
  >>>bill
  jack
  mary
  ```
  >如果下标超出范围，则会抛出异常

## 3.分片

分片操作是从序列A中获取一个子序列B。

- 基本操作如下：

  ```python
  s = "https://vineo.cn"
  
  print(s[1:3])
  >>>tt
  ```

- 通过索引和省略索引的方式得到子序列，观察下面一个例子：

  ```python
  a = [1, 2, 3, 4, 5, 6, 7, 8]
  print(a[3:5])
  print(a[0:1])
  print(a[5:8])
  print(a[-3:-1])
  print(a[-3:0]) #python语言规定，如果结束索引比开始索引晚出现，那么就会返回一个空序列。
  print(a[-3:])  #省略了结束索引 --->print(a[-3:-1])
  print(a[-3:8])  #结束索引用了正数作为索引
  print(a[:3]) #表示序列的前三位子序列
  print(a[:]) #如果不指定任何序列，则复制整个序列
  >>>
  [4, 5]
  [1]
  [6, 7, 8]
  [6, 7]
  []
  [6, 7, 8]
  [6, 7, 8]
  [1, 2, 3]
  [1, 2, 3, 4, 5, 6, 7, 8, 9]
  ```
- 设置步长，可以用来获取不相邻的元素
  ```python
  a = [1, 2, 3, 4, 5, 6, 7, 8]
  print(a[1:6:2]) #指定每次跨几步，格式是：   a[开始索引:结束索引:步长]
  print(a[::2]) #可以省略开始和结束索引
  print(a[3::2])
  print(a[::-2]) #从后往前推
  >>>
  [2, 4, 6]
  [1, 3, 5, 7, 9]
  [4, 6, 8]
  [9, 7, 5, 3, 1]
  ```
  >注意：步长不能为0，负责会抛出异常。如果步长为负数，此时开始索引要比结束索引要大。
- 小结：
  ```python
  urls = input("请输入一个网址")
  print("输入的scheme：", urls[0:5])
  print("输入的host：", urls[8:])

  >>>
  请输入一个网址https://www.vineo.com
  输入的scheme： https
  输入的host： www.vineo.com
  ```
  - 序列相加
  ```python
  print([1, 3, 4] + [5, 67])
  print([1,2,3]+["hrlloe"])
  print([1,2,3]+["hrlloe","23231",54])
  >>>
     [1, 3, 4, 5, 67]
     [1, 2, 3, 'hrlloe']
     [1, 2, 3, 'hrlloe', '23231', 54]
  ```
  >序列不能和字符串相加，不然会出现异常
- 序列相乘
  ```python
  print('hello' * 5)
  print([1,3,4]*5)
  >>>
  hellohellohellohellohello
  [1, 3, 4, 1, 3, 4, 1, 3, 4, 1, 3, 4, 1, 3, 4]
  ```
- 序列的长度（len），最大值（max）和最小值（min）
  ```python
  a = [34, 32, 4, 5123, 3232, 567, 89, 2, 2]
  print(len(a))
  print(max(a))
  print(min(a))
  >>>
  9
  5123
  2
  ```
  >注意点，序列中每一个值都是具有可比性，不然Python会报错
  >```python
  > a = ["dsada",2]
  > print(min(2)) # 报错
  >```
## 4.列表的操作
- 列表的元素赋值
  ```python
  a = [34, 32, 4, 5123, 3232, 567, 89, 2, 2]
  a[2] = "9"
  print(a)
  >>>
  [34, 32, '9', 5123, 3232, 567, 89, 2, 2]
  ```
  >注意点：赋值的索引可以是正数或者是负数，但是数值不能超过列表的索引的范围
- 列表元素的删除（del）
  ```python
  a = [34, 32, 4, 5123, 3232, 567, 89, 2, 2]
  del(a[1])
  print(a)
  >>>
  [34, 4, 5123, 3232, 567, 89, 2, 2]
  ```
- 分片赋值操作
分片赋值和分片获取字列表一样，也需要指定分片操作，也就是需要指定要操作的列表的范围。
  ```python
  # 将从列表的第一位开始替换元素，并且生成一个新的列表
  a = ["hello", "world", "python"]
  a[1:] = ["a", "b", "c"]
  print(a)

  # 使用list函数，将字符串转换为列表
  a= list("mick")
  print(a)
  a[1:] = "ary"
  print(a)
  >>>
  ['hello', 'a', 'b', 'c']
  ['m', 'i', 'c', 'k']
  ['m', 'a', 'r', 'y']
  ```
  >从上面的代码中，使用了分片，替换完成的子列表，可以是长度可以是不相同的。
- 因此我们可以以上特性，可以实现列表的数组的新增和删除。
  ```python
  a = [2, 3, 45, 6]
  a[1:1] = ["das", "ok", 23]
  print(a)

  a[1:3] = []
  print(a)

  >>>
  [2, 'das', 'ok', 23, 3, 45, 6]
  [2, 23, 3, 45, 6]
  ```
  >如果冒号前后数值相同，则表示不替换列表中任何元素。
## 5.列表方法
先来明确一个概念：函数和方法，函数是全局，而方法是定义在一个类中的。

| 方法名  |                             说明                             |
| :-----: | :----------------------------------------------------------: |
| append  |                      在列表最后插入新值                      |
|  clear  |                         清除列表内容                         |
|  copy   |                         复制一个列表                         |
|  count  |                统计列表中某个元素的出现的次数                |
| extend  | 在列表结尾插入一个新列表，类似于相加。不同点在于extend改变的是原列表，而相加得到一个新列表 |
|  index  |              获取元素在列表中第一次出现的索引数              |
| insert  |                     插入列表中指定的位置                     |
|   pop   |   移除列表中的元素(默认移除最后一位元素)，并且返回改元素值   |
| remove  |                移除列表中某个值的第一次匹配项                |
| reverse |                   将列表的元素进行反向存放                   |
|  sort   |             对列表进行排列，但是会改变原来的列表             |

## 6.元组

元组和列表一样，也是一种序列。不同点在于元组不能修改，它是只读属性，只需要用`,`分隔值即可。例如
```python
a = 1, 3, 4, 5, 6

print(a)
>>> (1, 3, 4, 5, 6)

() # 创建一个空元组

print(5*(12+4,)) # 生成5个同样值的元组
>>>(16,16,16,16,16)

print(5*(12+4)) #一个数值
>>>80

array = [1,4,5,6]
tuple(array) #可以使用tuple函数将列表转换为元组
```