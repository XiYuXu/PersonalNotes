>  参考链接https://www.bilibili.com/video/BV1oJ411U7Y8?t=1521  、https://zhuanlan.zhihu.com/p/49331510  、 https://zhuanlan.zhihu.com/p/26307123 、https://zhuanlan.zhihu.com/p/145706435

## SVM定义

> 支持向量机（support vector machine，常简称为SVM）是在分类与回归分析中分析数据的监督式学习模型与相关的学习算法。
>
> 是一个二分类的算法，目的是将样本空间中两个类别的点能被尽可能宽的明显的间隔（一个超平面）分开。
>
> 训练后对新的数据进行预测。

## **图示：**

>  二分类存在很多种划分的方法,比如下面有三种划分直线



![img](https://pic.downk.cc/item/5fdc0c5d3ffa7d37b318dc1e.png)

​																											图1-1  二分类划分方法多样

>  SVM就是找到其中分类间隔最大的超平面，试图让空间中**距离超平面距离最远的点**的与超平面间**距离值**最大。
>
> 如果我们找到一条足够粗的直线，其正好分离两个类，如下图所示，显然这种分类效果最好

![image-20201218095557237](https://pic.downk.cc/item/5fdc0c533ffa7d37b318d5a3.png)

​																								图1-2 最大间隔的分类

>  显然要找到距离最大的超平面，则必然为该粗线的中间的那条直线，且该切分平面是唯一的。



**所以我们的接下来的目标就是要定义这个直线的表达式。**

## 符号定义

#### 1.样本点的定义

![](https://pic.downk.cc/item/5fdd73c73ffa7d37b33c73b4.png)

定义单个样本点为上图中的(x<sub>1</sub>,y<sub>1</sub>),其中**x<sub>1</sub>**为d维的向量，y<sub>1</sub>则是最终的分类结果

#### **2.**超平面的定义

>  超平面定义为![[公式]](https://www.zhihu.com/equation?tex=%5Comega%5ETx%2Bb%3D0)，定义来源可参考笔记：https://github.com/XiYuXu/PersonalNotes/blob/master/%E6%95%B0%E5%AD%A6%E7%90%86%E8%AE%BA/%E8%B6%85%E5%B9%B3%E9%9D%A2.md

#### 3.间隔Margin的定义

现在我们有了一个超平面的表达式，只要把训练集样本点的坐标带入到这个表达式，就可以确定超平面中**W**和b的值。

然而有些临近或者落在超平面上的点，我们不希望有这样的情况，以免产生误分类的错误，因此可以定义一个更大的间隔。

**Margin**上下界表达式及图像如下图所示：

![](https://pic.downk.cc/item/5fdc13073ffa7d37b31d64d1.png)

也就是说必须让超平面与样本点存在一定的间隔，同时可以看到表达式右边是正负1，如果左右都同时乘以一个常数，则间隔也将随比例变化。



>  **注：**之后的拉格朗日对偶化可查阅开头所述链接