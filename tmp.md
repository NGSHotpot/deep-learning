
## 线性分类模型

在前面图像分类流程中，我们介绍了线性分类模型，可以将线性分类模型简化为![equation](http://latex.codecogs.com/gif.latex?Y=Wx)。容易知道，对于训练数据来说![equation](http://latex.codecogs.com/gif.latex?Y)和![equation](http://latex.codecogs.com/gif.latex?x)都是已知的，但是![equation](http://latex.codecogs.com/gif.latex?W)是未知的。前面一节的内容中是直接给出了一组![equation](http://latex.codecogs.com/gif.latex?W)的值，那么问题来了：这组权重是怎么得出来的？这组权重好吗？如果不好，怎么得到更好的权重？

本节的主要内容主要包括：

1. 如何评估已有的一组权重的好坏？损失函数（loss function）
2. 如何得到并优化权重？最优化（Optimization）


## 损失函数



