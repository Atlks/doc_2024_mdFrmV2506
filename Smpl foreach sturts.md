Smpl foreach sturts

十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:29]
十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:34]
简化循环 使用 map fltr模式

十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:37]
列表推导式（list comprehension），是程序设计语言的一类语法结构，用于基于描述创建一个列表（list）数据结构。相当于数学上的集合建构式符号。但不同于map与filter函数。

“list comprehension”没有统一的中文译法。有译作列表解析式、列表生成式、列表构建、列表理解等。

十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:38]
使用自定义fun也可简化佛操作

十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:38]
使用foreach函数也能简化for操作

十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:40]
Python 推导式
Python 推导式是一种独特的数据处理方式，可以从一个数据序列构建另一个新的数据序列的结构体。

Python 推导式是一种强大且简洁的语法，适用于生成列表、字典、集合和生成器。

在使用推导式时，需要注意可读性，尽量保持表达式简洁，以免影响代码的可读性和可维护性。

Python 支持各种数据结构的推导式：

列表(list)推导式
字典(dict)推导式
集合(set)推导式
元组(tuple)推导式

十 Adam 大鱼 刘洋 汤姆, [8/7/2024 上午 1:41]
字典推导式
字典推导基本格式：

{ key_expr: value_expr for value in collection }

或

{ key_expr: value_expr for value in collection if condition }
使用字符串及其长度创建字典：

实例
listdemo = ['Google','Runoob', 'Taobao']
# 将列表中各字符串值为键，各字符串的长度为值，组成键值对
>>> newdict = {key:len(key) for key in listdemo}
>>> newdict
{'Google': 6, 'Runoob': 6, 'Taobao': 6}
提供三个数字，以三个数字为键，三个数字的平方为值来创建字典

