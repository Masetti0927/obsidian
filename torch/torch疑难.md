# 训练神经网络时`w-=lr*w.grad`和`w=w-lr*w.grad`的不同

在训练神经网络时，使用`w-=lr*w.grad`时网络可以正常训练，但使用`w=w-lr*w.grad`时网络的梯度却消失。因为使用`w=w-lr*w.grad`时，w和w不是相同的w，而是将原先的w计算后存在一个新的tensor里再返回给新的w中。新的w没有设置梯度，所以训练会梯度消失。
原文链接：[https://blog.csdn.net/weixin_49327481/article/details/124075184]