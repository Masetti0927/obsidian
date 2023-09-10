
# list.sort()语法

```python
list.sort(cmp=None, key=None, reverse=False)
```
-  cmp – 可选参数, 如果指定了该参数会使用该参数的方法进行排序。
-  key – 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
-  reverse – 排序规则，reverse = True 降序， reverse = False 升序（默认）。
# [lambda](https://so.csdn.net/so/search?q=lambda&spm=1001.2101.3001.7020)语法

lambda关键字给我们提供了一个不用名字就能使用的函数。这个特性使得它非常适合用作函数的参数。lambda 函数的书写方式为，单词 lambda 后跟参数名列表，然后是单个代码块。参数列表和代码块由冒号分隔。这类似于 python 中的其他结构，比如 while、 for、 if 等等，它们都是具有代码块的语句。

lambda语法如下:
```python
lambda  参数列表  : 代码块
lambda parameter1,parameter2 : parameter1+parameter2
```
# 二者结合
```python
x = [
        ('john', 'A', 15),
        ('jane', 'B', 12),
        ('dave', 'B', 10),
        ('dave', 'B', 8),
]
x.sort(key=lambda i:i[2])
print(x)
```
- 代码中第一个i为形参，代表x中的某个元素
- ：为分割符号
- ：后面为代码块

输出
```python
[('dave', 'B', 8), ('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]
```
# 其他可能对你有用的
```python
list.sort(cmp=None, key=None, reverse=False)
key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
reverse -- 排序规则，reverse = True 降序， reverse = False 升序（默认）
```

```python
# 获取列表的第二个元素
def takeSecond(elem):
    return elem[1]
 
 
# 列表
# >>> (1,2,3,4)[1]
# 2
random = [(2, 2), (3, 4), (4, 1), (1, 3)]
# 指定第二个元素排序
random.sort(key=takeSecond)  # key主要是用来进行比较的元素，+
# 只有一个参数，具体的函数(takeSecond)的参数就是(elem)取自于可迭代对象中{(2,2)}+
# 指定可迭代对象(random)中的一个元素{eg:(2,2)}来进行排序。
#当然还可以用无头lambda表达式来搞:
random.sort(key=lambda elem: elem[1], reverse=True)
# 输出
print('排序列表：', random)
```

```python
In [1]: f00 = lambda x: x/2

In [2]: f00(10)
Out[2]: 5.0

In [3]: (lambda x: x/2)(10)
Out[3]: 5.0

In [4]: (lambda x, y: x / y)(10, 2)
Out[4]: 5.0

In [5]: (lambda: 'amazing lambda')() # func with no args!
Out[5]: 'amazing lambda'
```
# test
