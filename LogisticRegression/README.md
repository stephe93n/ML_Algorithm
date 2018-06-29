&emsp;&emsp;Logistic回归属于分类模型。回顾线性回归，输出的是连续的实数，而Logistic回归输出的是[0,1]区间的概率值，通过概率值来判断因变量应该是1还0(简单来说，它的结果不是1就是0)。因此，虽然名字中带着“回归”（输出范围常为连续实数），但Logistic回归属于分类模型（输出范围为一组离散值构成的集合）。  
&emsp;&emsp;最大熵原理认为，学习概率模型时，在所有可能的概率模型中，熵最大的模型是最好的模型。通常用约束条件来确定概率模型的集合，所以，最大熵原理也可以表述为在满足
约束条件的模型集合中选取熵最大的模型。  
 **当X服从均匀分布时，熵最大。**  
 &emsp;&emsp;最大熵模型的学习过程就是求解最大熵模型的过程。最大熵模型的学习可以形式化为约束最优化问题。  
 
 ### 模型学习的最优化方法
 
 &emsp;&emsp;logistic回归模型、最大熵模型学习归结为以似然函数为目标函数的最优化问题，通常通过 **迭代算法** 求解。  
 常见的优化方法有改进的 **迭代尺度法(IIS)、梯度下降法、牛顿法或拟牛顿法**。牛顿法或拟牛顿法一般收敛速度更快。

## logistic回归是如何工作的

Logistic 回归通过使用其固有的 logistic 函数估计概率，来衡量因变量（我们想要预测的标签）与一个或多个自变量（特征）之间的关系。   
然后这些概率必须二值化才能真地进行预测。这就是 logistic 函数的任务，也称为 sigmoid 函数。Sigmoid 函数是一个 S 形曲线，它可以将任意实数值映射到介于 0 和 1 之间的值，但并不会取到 0/1。然后使用阈值分类器将 0 和 1 之间的值转换为 0 或 1。   
下面的图片说明了 logistic 回归得出预测所需的所有步骤：  
<img  src="https://mmbiz.qpic.cn/mmbiz_png/KmXPKA19gWicMpaiaku5HZVfmoEL2hmBBficJdw7lyMLr99aG0fzOg6O28Z1NTeBdZAg8twVbgHrcTQ8qZtjLqfaQ/640?wx_fmt=png&amp;tp=webp&amp;wxfrom=5&amp;wx_lazy=1" width=400 height=256  >  

下面是 logistic 函数（sigmoid 函数）的图形表示：

<img src="https://mmbiz.qpic.cn/mmbiz_png/KmXPKA19gWicMpaiaku5HZVfmoEL2hmBBfPN0diby5s1yowicAhenEBUj5gibvvtSq7Y1EfjKm7Iw01Ir7WBu6piaurQ/640?wx_fmt=png&amp;tp=webp&amp;wxfrom=5&amp;wx_lazy=1" width=350 height=256>

我们希望随机数据点 **被正确分类的概率最大化**，这就是 **最大似然估计**。最大似然估计是统计模型中估计参数的通用方法。  
你可以使用不同的方法（如优化算法）来最大化概率。牛顿法也是其中一种，可用于查找许多不同函数的最大值（或最小值），包括似然函数。也可以用梯度下降法代替牛顿法。  

#### Logistic 回归 vs 线性回归 

&emsp;&emsp;逻辑回归得到一个离散的结果，但线性回归得到一个连续的结果。预测房价的模型算是返回连续结果的一个好例子。该值根据房子大小或位置等参数的变化而变化。离散的结果总是一件事（有）或另一个（没有）。  

#### 优缺点

**优点：**  
> Logistic 回归是一种被人们广泛使用的算法，因为它非常高效，不需要太大的计算量，又通俗易懂，不需要缩放输入特征，不需要任何调整，且很容易调整，并且输出校准好的预测概率。   
> 与线性回归一样，当去掉与输出变量无关的属性以及相似度高的属性时，logistic 回归效果确实会更好。因此特征处理在 Logistic 和线性回归的性能方面起着重要的作用。  
> Logistic 回归的另一个优点是它非常容易实现，且训练起来很高效。在研究中，我通常以 Logistic 回归模型作为基准，再尝试使用更复杂的算法。  

 **缺点：**  
 > 我们不能用 logistic 回归来解决非线性问题. 
 >  容易欠拟合，分类精度可能不高。  
 > 高度依赖正确的数据表示。  
 
 #### 适用场景  
 
 Logistic 回归通过线性边界将输入分成两个「区域」，每个类别划分一个区域。因此，数据应当是线性可分的，如下图所示的数据点：  
 <img src="https://mmbiz.qpic.cn/mmbiz_png/KmXPKA19gWicMpaiaku5HZVfmoEL2hmBBfSkTCOWcjBoUtZe0h2GicnDXNpur8F7l0EMuYDibiaEDXU6s4AF2Sljsxw/640?wx_fmt=png&amp;tp=webp&amp;wxfrom=5&amp;wx_lazy=1" width=350 height=256>  
 
 换句话说：当 Y 变量只有 **两个值** 时（例如，面临分类问题时），应该考虑使用逻辑回归。注意，也可以将 Logistic 回归用于多类别分类。
 
 
 
 