# M-P 模型

## 简介

1943年，McCulloch和Pitts在他们共同发表的文章《A Logical Calculus of Ideas Immanent in Nervous Activity》中提出深度学习的雏形M-P模型，本文将介绍这部分内容。

## 神经元

McCulloch是美国神经科学家，Pitts是数学家，他们合作做出的M-P模型。深度学习之前的名字叫神经网络，这跟其设计原理很相关。神经元是组成人类大脑的基本元素，主要包括树突、轴突、细胞体等结构。神经元工作原理可以简化为神经元通过树突或者细胞体等接受来至其他神经元轴突传递的信号，然后根据接收到的信号判断是否激活某个状态，通过轴突传递信号到下游神经元。
![]()

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
