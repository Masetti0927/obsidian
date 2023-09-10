
### 对于pyhon使用sort()方法出现：1, 10, 100, 101, 102 … 2, 20 …的情况

1.如果是对于纯数字字符串的排序：list1 = [“1”,“10”,“3”,“2”,“11”,“12”]
```python
list1 = [int(x) for x in list1] 
list1.sort()
```
或者
```python
list1.sort(key=int)
```
2.对于目录里文件名的排序：list1 = [“1.png”,“10.png”,“3.png”,“2.png”,“11.png”,“12.png”]
```python
list1.sort(key=lambda x:int(x.split('.')[0]))
```
