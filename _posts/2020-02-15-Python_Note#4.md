---
title: Python_Note#4
published: true
---
# Python学习笔记04
***
实验楼学习
***
## 数据结构
***
### 列表
* 建立列表：

```py
a = [1, 2, 3]
```

* 增加元素&插入元素：

```py
a.append(4) # 将4添加到列表末尾
a.insert(0, 111) # 在列表0位置添加元素 111

a = [111, 1, 2, 3, 4] # 此时列表a
```

* 列表其他操作：

```py
a.count(s) # 返回列表中 s 出现的次数
a.remove(s) # 删除指定元素
a.reverse(s) # 反转整个列表
a.extend(b) # 将列表b的所有元素添加到a列表的末尾
a.sort() # 将元素从小到大排序，前提是元素可比较
del a[-1] # 删除指定位置元素
```

* 将列表用作栈和队列：

```py
# 栈，LIFO后进先出
a.append() # 入栈
a.pop() # 出栈
# 队列，FIFO先进先出
a.append(1) # 入队
a.pop(0) # 出队
```

* 列表推导式：
    * 用于简便地创建列表：

```py
squares = [x**2 for x in range(10)]
combs = [(x, y) for x in [1, 2, 3] for y in [3, 1, 4] if x!=y]
# 列表推导式也可嵌套
z = [x + 1 for x in [x ** 2 for x in [1, 2, 3]]]
```

### 元组
* 元组是由数个逗号分割的值组成

```py
>>> a = 'Fedora', 'ShiYanLou', 'Kubuntu', 'Pardus'
>>> a
('Fedora', 'ShiYanLou', 'Kubuntu', 'Pardus')
>>> a[1]
'ShiYanLou'
>>> for x in a:
...     print(x, end=' ')
...
Fedora ShiYanLou Kubuntu Pardus
```

* 可对任何一个元组执行拆封操作并赋值给多个变量：

```py
>>> divmod(15,2)
(7,1)
>>> x, y = divmod(15,2)
>>> x
7
>>> y
1
```

* 元组是不可变类型，无法删除、添加：

```py
>>> a = (1, 2, 3, 4)
>>> del a[0]
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
TypeError: 'tuple' object doesn't support item deletion
copy
```

* 创建只含有一个元素的元组，在值后面跟一个逗号（不加逗号数据类型不是元组）：

```py
a = (123,)
type(a) = ‘tuple’
```

### 集合
* 无序不重复
* 基本操作：

```py
>>> basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
>>> print(basket)                      # 你可以看到重复的元素被去除
{'orange', 'banana', 'pear', 'apple'}
>>> 'orange' in basket
True
>>> 'crabgrass' in basket
False

>>> # 演示对两个单词中的字母进行集合操作
...
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a                                  # a 去重后的字母
{'a', 'r', 'b', 'c', 'd'}
>>> a - b                              # a 有而 b 没有的字母
{'r', 'd', 'b'}
>>> a | b                              # 存在于 a 或 b 的字母
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
>>> a & b                              # a 和 b 都有的字母
{'a', 'c'}
>>> a ^ b                              # 存在于 a 或 b 但不同时存在的字母
{'r', 'd', 'b', 'm', 'z', 'l'}
```

* 集合中添加或弹出元素：

```py
>>> a = {'a','e','h','g'}
>>> a.pop()  # pop 方法随机删除一个元素并打印
'h'
>>> a.add('c')
>>> a
{'c', 'e', 'g', 'a'}
```

### 字典
* 无序的键值对(key:value)
* 基本操作

```py
>>> data = {'kushal':'Fedora', 'kart_':'Debian', 'Jace':'Mac'}
>>> data
{'kushal': 'Fedora', 'Jace': 'Mac', 'kart_': 'Debian'}
>>> data['kart_']
'Debian'
copy
```
* 创建新的键值对：

```py
>>> data['parthan'] = 'Ubuntu'
>>> data
{'kushal': 'Fedora', 'Jace': 'Mac', 'kart_': 'Debian', 'parthan': 'Ubuntu'}
```

* del删除：

```py
>>> del data['kushal']
>>> data
{'Jace': 'Mac', 'kart_': 'Debian', 'parthan': 'Ubuntu'
```

* in查询是否存在：

```py
>>> 'ShiYanLou' in data
False
```

* dict()可以从包含键值对的元组中创建字典：

```py
>>> dict((('Indian','Delhi'),('Bangladesh','Dhaka')))
{'Indian': 'Delhi', 'Bangladesh': 'Dhaka'}
```

* items()方法遍历字典：

```py
>>> data
{'Kushal': 'Fedora', 'Jace': 'Mac', 'kart_': 'Debian', 'parthan': 'Ubuntu'}
>>> for x, y in data.items():
...     print("{} uses {}".format(x, y))
...
Kushal uses Fedora
Jace uses Mac
kart_ uses Debian
parthan uses Ubuntu
```

* dict.setdefault(key,default)的使用：

```py
>>> data = {}
>>> data.setdefault('names', []).append('Ruby')
>>> data
{'names': ['Ruby']}
>>> data.setdefault('names', []).append('Python')
>>> data
{'names': ['Ruby', 'Python']}
>>> data.setdefault('names', []).append('C')
>>> data
{'names': ['Ruby', 'Python', 'C']}
```

* dict.get(key, default)的使用：

```py
>>> data['foo']
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
KeyError: 'foo'
>>> data.get('foo', 0)
0 # 不存在key则返回default的值
```

* enumerate()遍历：

```py
>>> for i, j in enumerate(['a', 'b', 'c']):
...     print(i, j)
...
0 a
1 b
2 c
```

* zip()的使用：

```py
>>> a = ['Pradeepto', 'Kushal']
>>> b = ['OpenSUSE', 'Fedora']
>>> for x, y in zip(a, b):
...     print("{} uses {}".format(x, y))
...
Pradeepto uses OpenSUSE
Kushal uses Fedora
```