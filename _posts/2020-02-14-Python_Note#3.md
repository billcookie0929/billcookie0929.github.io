---
title: Python_Note#3
published: true
---
# Python学习笔记03
***
实验楼学习
***
## 控制流if-else
***
### if语句
语法：

```py
if expression:
    do this
```

### else/elif语句
语法：

```py
if expression:
    do this
elif expression:
    do this
else:
    do this
```

### 真值检测：
优雅方式：

```py
if x:
    pass
```

错误举例：

```py
if x == True:
    pass
```

## 循环
***
### while循环
语法：

```py
while condition:
    statement1
    statement2
```

### 列表
举例：

```py
a = [ 1, 342, 223, ‘India’, ‘Fedora’]
a[0] = 1
a[4] = ‘Fedora’
a[-1] = ‘Fedora’
```

#### 切片

```py
>>> a[0:-1]
>>> [1, 342, 223, ‘India’]
>>> a[2:-2]
>>> [223]
>>> a[:] #切片不会影响列表，而是拷贝副本
>>> [1, 342, 223, ‘India’, ‘Fedora’]
>>> a[:-2]
>>> [1, 342, 223]
>>> a[-2:]
>>> [‘India’,’Fedora’]
```
#### 索引过大

```py
>>> a[32]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
>>> a[-10]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
Python的优雅处理：

```py
>>> a[2:32]
[223, 'India', 'Fedora']
>>> a[32:]
[]
```

#### 设置步长

```py
>>> a[1::2]
>>> [342, ‘India’]
```

#### 列表相加

```py
>>> a + [36, 49, 64, 81, 100]
>>> [1, 342, 223, 'India', 'Fedora', 36, 49, 64, 81, 100]
```

#### 修改元素

```py
>>> cubes = [1, 8, 27, 65, 125]
>>> cubes[3] = 64
>>> cubes
[1, 8, 27, 64, 125]
```

```py
>>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> letters
['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> # 替换某些值
>>> letters[2:5] = ['C', 'D', 'E']
>>> letters
['a', 'b', 'C', 'D', 'E', 'f', 'g']
>>> # 现在移除他们
>>> letters[2:5] = []
>>> letters
['a', 'b', 'f', 'g']
>>> # 通过替换所有元素为空列表来清空这个列表
>>> letters[:] = []
>>> letters
[]
```

#### 检验元素

```py
>>> a = ['ShiYanLou', 'is', 'cool']
>>> 'cool' in a
True
>>> 'Linux' in a
False
copy
```

#### 列表长度

```py
>>> len(a)
3
```

检验列表是否为空：

```py
if a:
    pass
else:
    pass
```

#### 列表嵌套

```py
>>> a = ['a', 'b', 'c']
>>> n = [1, 2, 3]
>>> x = [a, n]
>>> x
[['a', 'b', 'c'], [1, 2, 3]]
>>> x[0]
['a', 'b', 'c']
>>> x[0][1]
'b'
```

### for循环
示例：

```py
>>> a = ['ShiYanLou', 'is', 'powerful']
>>> for x in a:
...     print(x)
...
ShiYanLou
is
powerful
```

```py
>>> a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> for x in a[::2]:
...     print(x)
1
3
5
7
9
```

#### range()函数
示例：

```py
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4
>>> range(1, 5)      
range(1, 5)
>>> list(range(1, 5))
[1, 2, 3, 4]
>>> list(range(1, 15, 3))
[1, 4, 7, 10, 13]
>>> list(range(4, 15, 2))
[4, 6, 8, 10, 12, 14]
```

### continue语句
作用：跳过本次循环进入下一次循环

```py
while condition:
    continue
```

### 循环的else语句：
在循环完毕后执行，除非break终止循环。

```py
for condition:
    do this
else:
    do this
```