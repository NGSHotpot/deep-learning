
## 线性分类模型

先介绍一个数据集CIFAR-10，在前面的内容中就提到了，但是一直没有介绍。CIFAR-10数据集中总共有60000张图片，其中50000张为训练集，另外10000张为测试集，所有的这些照片都属于10个分类，包括飞机、汽车、鸟、猫、鹿、狗、青蛙、马、船、卡车十类。这个一个典型的图像分类的数据集，其中每张图片的大小为 32 * 32 * 3，即宽度为32，高度为32，深度为3，所以总共有3072个像素。

若是将这3072个像素上的值用列向量![equation](http://latex.codecogs.com/gif.latex?x=\(x_1,x_2,...,x_n\) )表示，用![equation](http://latex.codecogs.com/gif.latex?n)表示每张图片上的像素数量，![equation](http://latex.codecogs.com/gif.latex?N)表示照片的数量。

那么对于第![equation](http://latex.codecogs.com/gif.latex?i)张照片我们可以使用![equation](http://latex.codecogs.com/gif.latex?Y_i=a_{i1}x_{i1}+a_{i2}x_{i2}+...+a_{in}x_{in})表示该照片的类别与其3072个像素间的线性关系，类似于多元线性回归，但是在这个例子里面不在是二分类，而是有十分类,且令![equation](http://latex.codecogs.com/gif.latex?W_i=X=\(a_{i2},x_{i2},...,x_{in}\) )，那么刚才说的线性模型在所有的![equation](http://latex.codecogs.com/gif.latex?k)个分类上就可以表示为![equation](http://latex.codecogs.com/gif.latex?Y=xW)。其中![equation](http://latex.codecogs.com/gif.latex?W)为一个矩阵，其大小为![equation](http://latex.codecogs.com/gif.latex?n\times{k})，![equation](http://latex.codecogs.com/gif.latex?x)为一个向量，其大小为![equation](http://latex.codecogs.com/gif.latex?1\times{n})![equation](http://latex.codecogs.com/gif.latex?Y)为一个向量，其大小为![equation](http://latex.codecogs.com/gif.latex?1\times{k})，其值的大小可以分别表示是否属于这![equation](http://latex.codecogs.com/gif.latex?k)个分类的衡量标准。
