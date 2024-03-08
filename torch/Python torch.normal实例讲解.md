2023.3/8
## 用法
```python 
torch.normal(mean, std, *, generator=None, out=None) → Tensor
```
## ①

### 参数
-  **mean**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")) -per-element 的张量表示
-  **std**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")) -per-element 标准差的张量
### 关键字参数：
- **generator**([torch.Generator](https://vimsky.com/examples/usage/python-torch.Generator-pt.html "torch.Generator")， 可选的) -用于采样的伪随机数发生器
- **out**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")_,__可选的_) -输出张量。

## ②
### 参数:
- **mean**([_float_](https://vimsky.com/cache/index.php?source=https%3A//docs.python.org/3/library/functions.html%23float "(in Python v3.10)")_,__可选的_) -所有分布的平均值
- **std**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")) -per-element 标准差的张量
### 关键字参数
- **out**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")_,__可选的_) -输出张量。

## ③
### 参数:
- **mean**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")) -per-element 的张量表示
- **std**([_float_](https://vimsky.com/cache/index.php?source=https%3A//docs.python.org/3/library/functions.html%23float "(in Python v3.10)")_,__可选的_) -所有分布的标准差

### 关键字参数：
- **out**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")_,__可选的_) -输出张量

## ④
### 参数：
- **mean**([_float_](https://vimsky.com/cache/index.php?source=https%3A//docs.python.org/3/library/functions.html%23float "(in Python v3.10)")) -所有分布的平均值
- **std**([_float_](https://vimsky.com/cache/index.php?source=https%3A//docs.python.org/3/library/functions.html%23float "(in Python v3.10)")) -所有分布的标准差
- **size**(_int..._) -定义输出张量形状的整数序列。

### 关键字参数：
- **out**([_Tensor_](https://vimsky.com/cache/index.php?source=https%3A//pytorch.org/docs/stable/tensors.html%23torch.Tensor "torch.Tensor")_,__可选的_) -输出张量。

返回从给出均值和标准差的独立正态分布中抽取的随机数张量。

[`mean`](https://vimsky.com/examples/usage/python-torch.mean-pt.html) 是一个张量，每个输出元素的正态分布均值

[`std`](https://vimsky.com/examples/usage/python-torch.std-pt.html) 是一个张量，每个输出元素的正态分布的标准差

[`mean`](https://vimsky.com/examples/usage/python-torch.mean-pt.html)和[`std`](https://vimsky.com/examples/usage/python-torch.std-pt.html)的形状不需要匹配，但每个张量的元素总数需要相同。

## 注意
- 当形状不匹配时，使用[`mean`](https://vimsky.com/examples/usage/python-torch.mean-pt.html)的形状作为返回输出张量的形状
- 当[`std`](https://vimsky.com/examples/usage/python-torch.std-pt.html) 是 CUDA 张量时，此函数将其设备与 CPU 同步。

## 例子
例子：

``` python
>>> torch.normal(mean=torch.arange(1., 11.), std=torch.arange(1, 0, -0.1))
tensor([  1.0425,   3.5672,   2.7969,   4.2925,   4.7229,   6.2134, 8.0505,   8.1408,   9.0563,  10.0566])
```

```python
torch.normal(mean=0.0, std, *, out=None) → Tensor
```

与上面的函数类似，但方法在所有绘制的元素之间共享。

例子：

```python
>>> torch.normal(mean=0.5, std=torch.arange(1., 6.))
tensor([-1.2793, -1.0732, -2.0687,  5.1177, -1.2303])
```

```python
torch.normal(mean, std=1.0, *, out=None) → Tensor
```

与上面的函数类似，但标准偏差在所有绘制的元素之间共享。

例子：

```python
>>> torch.normal(mean=torch.arange(1., 6.))
tensor([ 1.1552,  2.6148,  2.6535,  5.8318,  4.2361])
```

```python
torch.normal(mean, std, size, *, out=None) → Tensor
```

与上面的函数类似，但均值和标准差在所有绘制元素之间共享。结果张量的大小由 `size` 给出。

例子：

```python
>>> torch.normal(2, 3, size=(1, 4))
tensor([[-1.3987, -1.9544,  3.6048,  0.7909]])
```