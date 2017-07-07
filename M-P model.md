# M-P 模型

## 简介

1943年，McCulloch和Pitts在他们共同发表的文章《A Logical Calculus of Ideas Immanent in Nervous Activity》中提出深度学习的雏形M-P模型，本文将介绍这部分内容。

## 神经元

McCulloch是美国神经科学家，Pitts是数学家，他们合作做出的M-P模型。深度学习之前的名字叫神经网络，这跟其设计原理很相关。神经元是组成人类大脑的基本元素，主要包括树突、轴突、细胞体等结构。神经元工作原理可以简化为神经元通过树突或者细胞体等接受来至其他神经元轴突传递的信号，然后根据接收到的信号判断是否激活某个状态，通过轴突传递信号到下游神经元。

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/1.png)

图片来自维基百科（https://zh.wikipedia.org/wiki/%E7%A5%9E%E7%B6%93%E5%85%83）

## M-P模型

McCulloch和Pitts根据神经元传递信号的原理，通过数学模型对神经元工作模型进行简化，建立了M-P模型。对神经元他们做出如下假设：

>1. The activity of the neuron is an "all-or-none" process.
>2. A certain fixed number of synapses must be excited within the period of latent addition in order to excite a neuron at any time, and this number is independent of previous activity and position on the neuron. 
>3. The only significant delay within the nervous sytem is synaptic delay. 
>4. The activity of any inhibitory synapse absolutely prevents excitation of the neuron at that time.
>5. The structure of the net does not change with time. 

模型假设第一点是说神经元输入和输出的信号都看做二值信号，即要么激活要么不激活，只有1（激活）和0（不激活）两种状态。

模型假设第二点是说神经元在任意时刻要想激活当前神经元，需要所以传递给他的信号中的激活信号达到某个固定值，且这个值与神经元激活与否状态相互独立，与神经元位置相互独立。说白了，就是说要激活神经元传递进去的信号要到达某个特定的阈值（threshold）。

模型假设第三点是说某个神经元接收信号是同时接收所有的信号，不存在先接收哪个信号，后接收哪个信号的情况。

模型假设第四点是说起抑制作用的信号和其刺激作用的信号是同时发生的，即会相互抵消。

模型假设第五点是说某个神经元的结构是不改变。

在这五点假设的基础上，McCulloch和Pitts提出了他们的M-P模型。

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/2.png)

上图中的![equation](http://latex.codecogs.com/gif.latex?X_1,X_2,X_3)模型的是其他不同的神经元给当前神经元传递的信号，其中![equation](http://latex.codecogs.com/gif.latex?X_1,X_2,X_3)可以取0或者1。![equation](http://latex.codecogs.com/gif.latex?Y)也可以取值0（不激活）或者1（激活），代表该神经受到刺激后的输出。![equation](http://latex.codecogs.com/gif.latex?w_1,w_2,w_3)分别对应为![equation](http://latex.codecogs.com/gif.latex?X_1,X_2,X_3)的权重，该权重可以取正值代表刺激作用，取负值代表抑制作用。![equation](http://latex.codecogs.com/gif.latex?threshold)代表阈值，即要激活当前神经元需要的信号强度。

下面举个例子来说明该模型的工作情况。若设定![equation](http://latex.codecogs.com/gif.latex?w_1=1,w_2=1,w_3=1,X_1=1,X_2=0,X_3=1,threshold=2)，输入信号经过加权得到![equation](http://latex.codecogs.com/gif.latex?X_1w_1+X_2w_2+X_3=2\geq{threshold}),所以输出的信号![equation](http://latex.codecogs.com/gif.latex?Y=1)。

上面的模型是经过修饰的，原始的M-P模型展示形式不是这样的。我们首先来看一下原文中的图。

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/3.png)

图片来自《A Logical Calculus of Ideas Immanent in Nervous Activity》

原文是通过上面的图形及一大堆数学公式来展示M-P模型的。

## 理解M-P模型

我们先简单解释刚才给出的图形所代表的意义。主要有两个类型的子图形：

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/4.png)

看到上面有两种不同的信号输入，一种是黑色实心的叫激活信号，另外一种是空心的叫抑制信号。

下面我们使用M-P模型来表示常见的逻辑门

1. NOT（非门）

非门取反，若是输入为1则输出0，输入为0则输出1。

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/5.png)

给一个固定的激活信号，且权重为1，输入作为一个抑制信号传递给神经元，那么若输入为1，那么被抑制后传递信号-1，与固定激活信号1相互抵消，小于阈值1，输出信号0。同样的，若是输入信号为0，得到激活信号1，等于阈值1，所以输出信号1。

2. AND （与门）

与门取交，若输入的两个信号同时为1，则输出1，否则输出0

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/6.png)

上述模型中，取权重都为1，threshold为2，那么只有当输入信号都为1的时候，1+1=2才可能使得神经元激活。

3. OR （或门）

或门取并，若输入信号中至少有一个1，那么输出1，否则输出0

![](https://github.com/NGSHotpot/deep-learning/blob/master/images/M-P/6.png)

还是这个图，需要改变的只是将threshold改为1即可。

## M-P模型的问题

上面说了M-P模型可以表示非门、与门、或门，但是我们还知道一个异或门，M-P模型是否能表示异或门呢？M-P模型的问题就在这里，单层的M-P模型是无法解决异或问题的，因为异或问题是线性不可分问题，而M-P模型是线性模型。但是若是使用将多个M-P神经元组成多层的M-P模型就可以解决异或问题啦。

## 参考文献

1. A Logical Calculus of Ideas Immanent in Nervous Activity
2. http://ecee.colorado.edu/~ecen4831/lectures/NNet2.html
3. https://zh.wikipedia.org/wiki/%E7%A5%9E%E7%B6%93%E5%85%83
