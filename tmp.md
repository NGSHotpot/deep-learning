
## 线性分类模型

先介绍一个数据集CIFAR-10，在前面的内容中就提到了，但是一直没有介绍。CIFAR-10数据集中总共有60000张图片，其中50000张为训练集，另外10000张为测试集，所有的这些照片都属于10个分类，包括飞机、汽车、鸟、猫、鹿、狗、青蛙、马、船、卡车十类。这个一个典型的图像分类的数据集，其中每张图片的大小为 32 * 32 * 3，即宽度为32，高度为32，深度为3，所以总共有3072个像素。

若是将这3072个像素上的值用列向量![equation](http://latex.codecogs.com/gif.latex?x=\(x_1,x_2,...,x_n\) )表示，用![equation](http://latex.codecogs.com/gif.latex?n)表示每张图片上的像素数量，![equation](http://latex.codecogs.com/gif.latex?N)表示照片的数量。

那么对于第![equation](http://latex.codecogs.com/gif.latex?i)张照片我们可以使用![equation](http://latex.codecogs.com/gif.latex?Y_i=a_{i1}x_{i1}+a_{i2}x_{i2}+...+a_{in}x_{in})表示该照片的类别与其3072个像素间的线性关系，类似于多元线性回归，但是在这个例子里面不在是二分类，而是有十分类,且令![equation](http://latex.codecogs.com/gif.latex?W_i=X=\(a_{i2},x_{i2},...,x_{in}\) )，那么刚才说的线性模型在所有的![equation](http://latex.codecogs.com/gif.latex?k)个分类上就可以表示为![equation](http://latex.codecogs.com/gif.latex?Y=Wx)。其中![equation](http://latex.codecogs.com/gif.latex?W)为一个矩阵，其大小为![equation](http://latex.codecogs.com/gif.latex?{k}\times{n})，![equation](http://latex.codecogs.com/gif.latex?x)为一个向量，其大小为![equation](http://latex.codecogs.com/gif.latex?n\times{1})![equation](http://latex.codecogs.com/gif.latex?Y)为一个向量，其大小为![equation](http://latex.codecogs.com/gif.latex?k\times{1})，其值的大小可以分别表示是否属于这![equation](http://latex.codecogs.com/gif.latex?k)个分类的衡量标准。通常在操作时，还会在末尾加上一个偏移项，也是一个向量，大小为![equation](http://latex.codecogs.com/gif.latex?k\times{1})，然后线性模型就表示为![equation](http://latex.codecogs.com/gif.latex?Y=Wx+b)。


在上面的问题中，![equation](http://latex.codecogs.com/gif.latex?x)大小为![equation](http://latex.codecogs.com/gif.latex?3072\times{1})，![equation](http://latex.codecogs.com/gif.latex?W)的大小为![equation](http://latex.codecogs.com/gif.latex?10\times{3072})，![equation](http://latex.codecogs.com/gif.latex?b)的大小为![equation](http://latex.codecogs.com/gif.latex?10\times{1})。

## 线性分类示例

下图为线性分类的一个示例。

![](https://github.com/NGSHotpot/deep-learning/blob/master/stanford_img/lecture2/021.png)

假如下面的图片只有四个像素，且我们只需要将其分成三类，那么问题就简化成了上图所示的模型。上面的矩阵乘法计算之后得到的最后向量的值分别表示该图片是猫的数值，是狗的数值以及是船的数值。在这个示例中，狗的取值最大，所以被错误的分类为狗。显然通过调整上面的权重和偏移值可能得到正确的结果。

## 线性不可分问题

线性分类很直观，但是对于很多样的线性不可分问题难以解决。如下面的三个示例，比较直观是的第二个和第三个示例，第二个示例就是判断是否属于中间的圆环，显然是线性不可分的，第三个示例就是判断是否属于三个独立的圆区域，也是线性不可分的。

![](https://github.com/NGSHotpot/deep-learning/blob/master/stanford_img/lecture2/022.png)

## 待续

1. 损失函数（loss function）
2. 最优化（optimization）
3. 卷积神经网络（ConvNets）

