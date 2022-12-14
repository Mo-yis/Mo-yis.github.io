---
layout: posts
title: Python 笔记
---


# 安装 IPython

```bash
$ pip install ipython
```
- IPython 是一款优秀的 Python 命令行 REPL 应用程序




# 将 Python 文件转为 Shell 脚本

- 在文件中添加
```python
#!/usr/bin/python
```
- 设置可执行权限
```bash
$ chmod u+x <file_name>
```




# 多个变量赋值

- 可在一行代码中给多个变量赋值
```python
x, y, z = 10, 20, 30
# x = 10
# y = 20
# z = 30
```




# Python 数据类型

- 常见数据类型及转化 (使用构造函数)

| 数据类型 | 说明 |
| --- | --- |
| `str()` | 字符串型 |
| `int()` | 整型 |
| `float()` | 浮点型 |
| `complex()` | 复数 |
| `bool()` | 布尔值 |
| `list()` | 列表 |
| `tuple()` | 元组 |
| `range()` | 范围 |
| `dict()` | 字典 |
| `set()` | 集合 |

- 检查数据类型的函数

| 函数 | 说明 |
| --- | --- |
| `type(obj)` | 将变量作为参数, 返回变量类型 |
| `isinstance(obj, type)` | 检查类型是否匹配, 返回布尔值 |





# 字符串操作

- 使用 `+` 运算符拼接字符串
- 使用 `+=` 运算符附加字符串
- 使用 `str()` 将其他类型转字符串
- 使用 `"""` 或 `'''` 创建多行字符串
- 使用 `in` 运算符检查是否包含某个子字符串
- 使用 `\` 转义字符串中的特殊符号
- 使用 `[]` 运算符索引字符串

- 字符串内置方法

| 函数 | 说明 |
| --- | --- |
| `isalpha()` | 检查字符串是否只包含字母字符，并且不为空字符串 |
| `isalnum()` | 检查字符串是否只包含字母字符或数字字符，并且不为空 |
| `isdecimal()` | 检查字符串是否只包含十进制字符，并且不为空 |
| `lower()` | 获取字符串的小写版本 |
| `islower()` | 检查字符串是否全为小写 |
| `upper()` | 获取字符串的大写版本 |
| `isupper()` | 检查字符串是否全为大写 |
| `title()` | 所有单词首字母大写 |
| `startswith()` | 检查字符串是否以特定子字符串开头 |
| `endswith()` | 检查字符串是否以特定子字符串结尾 |
| `replace()` | 替换字符串的一部分 |
| `split()` | 按特定分隔符拆分字符串 |
| `strip()` | 修剪字符串中的空格, 另外还有 `lstrip()` 和 `rstrip()` |
| `join()` | 将字符串添加到另一个可迭代对象生成的字符串中 |
| `find()` | 查找特定子字符串在字符串中的位置 |
| `eval()` | 执行一个字符串表达式，并返回表达式的值 |
| `format()` | 字符串格式化打印 |
| `len()` | 检查字符串的长度 |
| `center()` | 字符串居中 |
| `count()` | 统计子字符串出现的次数 |

- 以上方法都不会改变原始字符串，它们将会返回一个新的、修改后的字符串
- `format()` 方法的格式控制:

| : | <填充> | <对齐> | <宽度> | <,> | <.精度> | <类型> |
|: - :|: ------- :|: ------- :|: ------- :|: ---- :|: ------- :|: -------- :|
| 引导符号 | 填充的单个字符 | <左对齐 | 格式化宽度 | 数值千位分隔符 | 浮点数精度 | 数据类型 |
|         |       | >右对齐 |      |    | 或字符串的最大长度 | 整数: b,c,d,o,x,X |
|      |          | ^居中对齐 |     |    |                | 浮点数: e,E,f,% |




# 布尔值操作

- 检查布尔类型

| 函数 | 说明 |
| --- | --- |
| `isinstance(obj, type)` | 检查类型是否匹配, 返回布尔值 |
| `any(obj)` | 参数传递的可迭代对象（如列表）中的任意一个值是 `True` 时，它就会返回 `True` |
| `all(obj)` | 当传递给它的所有值都是 `True` 时，才返回 `True` |




# 数字操作函数

| 函数 | 说明 |
| --- | --- |
| `abs()` | 返回一个数的绝对值 |
| `complex(var1, var2)` | 构造一个复数, 使用 `.real` 和 `.imag` 访问实部和虚部 |
| `round()` | 四舍六入五成双 |





# 列表 (元组) 类型

- 列表可以按顺序保存不同的数据类型值, 使用 `[]` 创建列表
- 索引可以是正数, 也可以是负数, 如 `items[-1]` 表示最后一个元素
- 使用 `in` 运算符检查某个元素是否存在于列表
- 使用 `items.index()` 或 `[]` 访问某个位置的元素
- 使用 `[ : : ]` 按步长切片提取列表元素 (**左闭右开区间**)
- 元组是列表的不可变版本, 使用 `()` 创建元组
- 使用 `items.index()` 获取索引对应的元素

## 附加新元素

```python
items += [元素, 元素, ...]

items.extend([元素, 元素, ...])

items.append(元素)
```

> 注意：使用`extend()`或`+=`不要忘记方括号。不要执行`items += "Test"`或`items.extend("Test")`，否则 Python 会在列表中添加 4 个单独的字符，即`['T', 'e', 's', 't']`

## 移除元素

```python
items.remove(元素)
# 只删除第一次出现的该元素

del items[索引]

items.pop(索引)
# 弹出指定索引的元素并返回该元素
# 默认弹出列表末尾的元素
```

## 插入元素

```python
items.insert(索引, 元素)

items[1:1] = ["Test1", "Test2"]
# 这里实际上是先删除再添加
# 就该例子来说，先删除[1:1]的元素，再在删除的位置上添加 
# （切片是左闭右开，所有[1:1]没有选中任何元素） 
# 比如 s = [1,2,3];  s[0:2] = ['a', 'b', 'c'];
# 执行完这两个语句，s 就变为['a', 'b', 'c', 3]
```

## 排序元素

```python
items.sort()
# 默认对字符串先排序大写, 这将永久性改变列表
# 参数 key=str.lower 将先排序小写字母
# 参数 reverse=True 将反转排序顺序

sorted(items)
# 返回一个已排序的列表副本
# 参数 reverse=True 将反转排序顺序

items.reverse()
# 永久性反转列表元素的排列顺序

list(reversed(items))
# 返回一个已反转的列表副本
```
> 注意：`sort()` 仅在列表包含可比较的值时才有效。例如，无法比较字符串和整数，如果您尝试（对元素之间不可比较的列表进行排序），您将看到到类似`TypeError: '<' not supported between 'int' and 'str'`的错误。




# 字典 (集合) 类型

- 使用 `{}` 创建集合, 使用 `{key: value}` 创建字典
- 字典的 key 是任何不可变的值, value 可以是任意类型
- 可以使用 `in` 运算符检查 key 是否包含在字典或集合中
- 字典的 value 可以嵌套字典和列表
- 从 Python3.7 起, 字典排列顺序与添加顺序相同
- 字典中的 key 是唯一的, 集合中的元素也是唯一的
- 集合没有顺序, 但可以使用 `sorted(sets)` 获取已排序的列表
- 使用 `&` 求集合的交集; 使用 `|` 求并集; 使用 `-` 求差集
- 使用 `>` 或 `<` 检查一个集合是否是另一个集合的超集或子集

## 添加或修改键值对

```python
dicts[key] = value
```

## 删除键值对

```python
dicts.pop(key)
# 检索键的值, 从字典中删除该键/值对
# 返回对应的 value

del dicts[key]

dicts.popitem()
# 检索并删除最后一个插入字典的键/值对
```

## 获取字典键

```python
dicts.keys()
# 返回一个 list 类型的键列表
```

## 获取字典值

```python
dicts[value]

dicts.values()
# 返回一个 list 类型的值列表
```

## 获取字典键值对

```python
dicts.get(key, default)
# 当字典中不存在该键时, 返回 default
# 若不传入第二个参数, 键不存在时返回 None

dicts.items()
# 返回两个 list 类型的键和值列表
```




# 自定义函数

> 形参通过引用传递。Python中的所有内容都是对象，但其中一些是不可变的，包括整数、布尔值、浮点数、字符串和元组。这意味着如果您将它们作为参数传递给函数，并在函数内部修改它们的值，则新值不会反映在函数外部

> 如果传递一个可变的对象，并且（在函数内部）更改了它的一个属性，则该更改将反映在外部

- `return` 可以不返回值, 也可以返回多个值, 只需使用逗号分隔, 这将返回一个元组



# 对象

- Python 中的一切都是**对象**, 具有可以使用点语法访问的**属性**和**方法**
- 函数 `id()` 检查特定对象在内存中的位置
- 一些类型的对象是**可变的***, 而另一些是**不可变的**, 这取决于对象本身
- 如果对象提供改变其内容的方法, 那么它是可变的, 否则它是不可变的

## 对象的地址

- 如果给变量赋不同的值，它的地址会改变，因为变量已经指向存储在内存中另一个位置的另一个值 (不可变的)

```python
age = 8
print(id(age))
# 140535918671808

age = 9
print(id(age))
# 140535918671840
```

- 但是，如果您使用对象的方法修改该对象，其内存地址将保持不变 (可变的)

```python
items = [1, 2]
print(id(items))
# 140093713593920

items.append(3)

print(items)
# [1, 2, 3]

print(id(items))
# 140093713593920
```



