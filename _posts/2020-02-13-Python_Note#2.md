---
title: Python_Note#2
published: true
---
# Python学习笔记02
***
实验楼学习
***
## 变量和数据类型
***
### 关键字和标识符
#### Python关键字：

```python
False        def        if        raise         None
del         import          return          True        elif
in          try         and         else        is
while       as      except      lambda          with
assert          finally         nonlocal        yield           break
for         not         class           from            or
continue            global          pass 
```

* 在解释器输入此命令可得到关键词列表：

```python
>>> keywords
```

#### Python数据类型：
* Python中不需特别定义数据类型
* 输入什么类型定义什么类型

```python
>>> a = 13
>>> b = 23
>>> a + b
36
```

#### 从键盘读取输入——input()函数：

```python
#!/use/bin/env python3
number = int(input(“Enter an integer:”))
if number <= 100:
    print(“Your number is less than or equal to 100”)
else:
    print(“Your number is greater than 100”)     
```

#### 字符串的格式化：
* str.format()函数
* {:.2f}——替换为2位精度的浮点数

#### 单行定义多个变量和赋值：

```python
>>> a, b = 45, 54
>>> a
45
>>> b
54
```

```python
>>> a, b = b, a #用来交换两个数的值
>>> a
54
>>> b
45
```

* 元组拆封：

```python
>>> data = (“shiyanlou”,”China”,”Python”)
>>> name, country, language = data
>>> name
‘shiyanlou’
>>> country
‘China’ 
>>> language
‘Python’ 
```
***
## 运算符和表达式
***
#### 运算符
* 数学运算符：

```python
a + b #加
a - b #减
a * b #乘
a / b #除（小数）
a // b #整除
a % b #求余
a += b #简写运算符 a = a + b
```

* 关系运算符：

```python
<
<=
>
>=
==
!=
```

* 逻辑运算符：

```python
and
or
not
```

#### 表达式
* 注意运算符的运算顺序

#### 类型转换

```py
float()
int()
str()
```