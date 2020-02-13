---
title: Python_Note#1
published: true
---

# Python学习笔记01
实验楼学习
***
## 基本背景
***
### 解释器
交互式运行Python代码

```python
>>>print(“Hello World!”)
Hello World!
```
### 脚本文件
.py文件运行Python代码
### Linux系统中使用Vim编程
```shell
`$ vim test.py
``` 
vim键盘图：

![](https://github.com/billcookie0929/Personal_Practice/blob/master/Python/Note/wm.jpg)
按i进入插入模式，输入代码：

```
#!/use/bin/env python3
print(“Hello World!”)
```
为文件添加权限：

```
$` chmod +x helloworld.py
```
执行脚本文件：

```
$` ./helloworld.py
```
### 代码风格
* 四个空格缩进。
* 函数之间空一行。
* 类之间空两行
* 字典、列表、元组以及参数列表中，在“，”后添加一个空格；字典中，“：”也添加一个空格。
* 赋值运算符和比较运算符周围要有空格（参数列表中除外），括号里不加空格。

### 注释
注释：用文本来解释这段代码是做什么的。
Python的注释是以#字符开始的：

```python
>>> # 这是一个注释
>>> # 下面这一行是求两数之和
>>> a = 12 + 34
>>> print(a) # 这里也是注释
```
### 模块

```python
>>>import math
>>>print(math.e)
```